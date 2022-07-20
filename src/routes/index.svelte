<script>
  import { browser } from '$app/env';
  import Grid from '../lib/Grid.svelte';
  import { wordList } from '../lib/wordList';
  import cards from '../lib/cards.json';
  export let gridArray = [
    [
      {
        word: '',
        pattern: ''
      }
    ]
  ];
  const populateGrid = () => {
    if (browser) {
      const gridDiv = document.querySelector('.bg-animation');
      if (gridDiv) {
        const cs = getComputedStyle(gridDiv);
        const w = parseInt(cs.width);
        const h = parseInt(cs.height);
        const remPX = parseFloat(getComputedStyle(document.documentElement).fontSize);
        const cellWidth = 4 * remPX;
        const cellHeight = remPX + 5;
        const cols = Math.floor(w / cellWidth);
        const rows = Math.floor(h / cellHeight);
        const getRandom = (m = 3) => crypto.getRandomValues(new Uint32Array(1))[0] % m;
        for (let i = 0; i < rows; i++) {
          if (gridArray[i] === undefined) gridArray[i] = [];
          for (let j = 0; j < cols; j++) {
            gridArray[i][j] = {
              word: wordList[getRandom(wordList.length)].slice(0, 4) || 'test',
              pattern: 'is-plain'
            };
          }
        }
        const resetPattern = () => [
          {
            row: (Math.floor(rows / 2) + getRandom() - 1 + rows) % rows,
            col: (Math.floor(cols / 2) + getRandom() - 1 + cols) % cols
          }
        ];
        let patternArray = resetPattern();
        const patternNextCell = () => {
          const i = patternArray.length;
          // if we have 11 words, pause then restart
          if (i === 12) {
            // make non selected invisible
            // gridArray.forEach((r) =>
            //   r.forEach((c) => {
            //     if (c.pattern === 'is-plain') c.pattern = 'is-hidden';
            //     else console.log('c.pattern :>> ', c.pattern);
            //   })
            // );
            // restart process
            setTimeout(populateGrid, 5000);
            return;
          }
          const x = getRandom() - 1;
          const y = getRandom() - 1;
          // can't choose the same cell
          if (!x && !y) {
            patternNextCell();
            return;
          }
          const l = patternArray[i - 1];
          const next = {
            row: (l.row + x + rows) % rows,
            col: (l.col + y + cols) % cols
          };
          // check this is a new cell
          const unique = !patternArray.find((c) => c.row === next.row && c.col === next.col);
          if (!unique) {
            patternNextCell();
            return;
          }
          patternArray.push(next);
          // change the class
          gridArray[next.row][next.col].pattern = 'is-pattern';
          // wait a second before furthering the pattern
          setTimeout(patternNextCell, 1000);
        };
        patternNextCell();
      }
    }
  };
  if (browser) {
    requestAnimationFrame(populateGrid);
  }
</script>

<div class="bg-animation">
  <Grid tableData={gridArray} />
  <div class="overlay">
    <div class="welcome">
      <h1>BORDER WALLETS</h1>
      <h2>Introducing a new way to quickly and reliably memorise Bitcoin seed phrases.</h2>
    </div>
    <div class="btn-container">
      <a href="/docs" class="btn btn-primary">Learn How</a>
      <a href="/docs/download-the-entropy-grid-generator" class="btn">Download EGG</a>
    </div>
  </div>
</div>
<div class="card-holder">
  {#each cards as card}
    <div class="card">
      <h3 class="card-title">{card.title}</h3>
      <p class="card-description">{card.description}</p>
      <div class="card-link">
        <a class="card-link-anchor" href={card.link}>{card.linkText}</a>
      </div>
    </div>
  {/each}
</div>
<div class="videoWrapper">
  <iframe
    title="How to Easily Memorise a Bitcoin Seed Phrase - using Border Wallets &amp; Entropy Grids"
    width="560"
    height="315"
    src="https://bitcointv.com/videos/embed/30df0582-b070-450d-8a9a-51fa0f8c463a"
    frameborder="0"
    allowfullscreen
    sandbox="allow-same-origin allow-scripts allow-popups"
  />
</div>

<style>
  .videoWrapper {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 */
    height: 0;
  }
  .videoWrapper iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  .bg-animation {
    width: 100%;
    height: calc(100vh - 96px);
    height: calc(100svh - 96px);
    background-color: var(--bg-color);
    color: var(--primary-color);
    position: relative;
    margin-top: -1rem;
  }
  .overlay {
    color: var(--accent-color);
    text-shadow: 2px 2px 10px black;
    text-align: center;
    position: absolute;
    width: 100%;
    height: 100%;
    padding: 10%;
    /* background-color: #00000055; */
    top: 0;
  }
  .btn-container {
    margin: 0 auto;
    padding: 1rem;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    position: absolute;
    bottom: 20%;
    width: 80%;
  }
  .btn {
    border: 1px solid var(--accent-color);
    max-width: 20rem;
    padding: 1rem;
    border-radius: 1rem;
    background-color: var(--header-bg-color);
    text-decoration: none;
    cursor: pointer;
    text-align: center;
    text-shadow: none;
    margin: 1rem;
  }
  .btn-primary {
    color: var(--header-bg-color);
    border-color: var(--header-bg-color);
    background-color: var(--accent-color);
  }
  .welcome {
    background-color: #383e42dd;
    padding: 1rem;
    border-radius: 2rem;
    margin-bottom: 1rem;
  }
  .card-holder {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
    padding-top: 25vh;
    flex-wrap: wrap;
  }
  .card {
    margin: 20px;
    padding: 20px;
    width: 400px;
    min-height: 200px;
    display: grid;
    grid-template-rows: 20px 50px 1fr 50px;
    border-radius: 10px;
    box-shadow: 0px 6px 10px rgba(0, 0, 0, 0.25);
    transition: all 0.2s;
    background-color: var(--alt-bg-color);
    color: var(--secondary-color);
  }

  .card:hover {
    box-shadow: 0px 6px 10px rgba(0, 0, 0, 0.4);
    transform: scale(1.01);
  }
  .card-link-anchor {
    position: relative;
    text-decoration: none;
    color: var(--accent-color);
  }

  .card-link-anchor::after {
    position: absolute;
    top: 25px;
    left: 0;
    content: '';
    width: 0%;
    height: 3px;
    background-color: var(--accent-color);
    transition: all 0.3s;
    text-shadow: 1px 1px 1px #00000055;
  }

  .card-link-anchor:hover::after {
    width: 100%;
  }
  .card-title {
    grid-row: 1/2;
    justify-self: center;
  }
  .card-description {
    grid-row: 3/4;
    font-weight: 400;
  }
  .card-link {
    grid-row: 4/5;
    align-self: center;
    justify-self: center;
    background-color: #383e42dd;
    padding: 1em;
    border-radius: 1em;
  }
  @media (max-width: 1600px) {
    .card-holder {
      justify-content: center;
    }
  }
</style>
