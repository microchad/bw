<script>
  import { browser } from '$app/env';
  import Grid from '../lib/Grid.svelte';
  import { wordList } from '../lib/wordList';
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
        const getRandom = (m = 3) => crypto.getRandomValues(new Uint8Array(1))[0] % m;
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
            row: Math.floor(rows / 2) + getRandom() - 1,
            col: Math.floor(cols / 2) + getRandom() - 1
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

<h2>TLDR:</h2>
<p>
  Memorising Bitcoin seed phrases (typically between 12 and 24 randomised words) can be difficult.
  By exploiting a phenomenon known as the Picture Superiority Effect, we have devised a way make it
  significantly easier to do this - using user-generated patterns.
</p>
<p>
  To assist with this process and make it robust and secure, we have created a tool (the Entropy
  Grid Generator - or EGG) that randomises all 2048 Bitcoin BIP39 seed words and presents them back
  to users as unique, randomised matrices; we call these 'Entropy Grids'.
</p>
<p>
  When users generate their Entropy Grid, they apply their own choice of pattern(s) to them, therein
  unlocking each applicable seed word to create uniquely memorable wallets; we call these 'Border
  Wallets'.
</p>
<p>
  For more information on how we do this, to access our Entropy Grid Generator (EGG), and for
  instructions on how to create your own Border Wallet, read our <a href="/docs">Documentation</a> section
  in detail.
</p>
<p>
  If you are already familiar with our Docs section, you can download the EGG <a
    href="/docs/download-the-entropy-grid-generator">here</a
  >.
</p>

<style>
  .bg-animation {
    width: 100%;
    height: calc(100vh - 96px);
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
</style>
