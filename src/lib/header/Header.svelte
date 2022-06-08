<script>
  import { page } from '$app/stores';
  import logo from './bw.svg';
  let navOpen = false;
  function toggleNav() {
    navOpen = !navOpen;
  }
</script>

<header>
  <div class="corner">
    <a href="/">
      <img src={logo} alt="BorderWallets.com" />
    </a>
  </div>

  <div class="corner">
    <svg
      class="ham hamRotate ham4 {navOpen ? 'active' : ''}"
      viewBox="0 0 100 100"
      width="80"
      on:click={toggleNav}
    >
      <path
        class="line top"
        d="m 70,33 h -40 c 0,0 -8.5,-0.149796 -8.5,8.5 0,8.649796 8.5,8.5 8.5,8.5 h 20 v -20"
      />
      <path class="line middle" d="m 70,50 h -40" />
      <path
        class="line bottom"
        d="m 30,67 h 40 c 0,0 8.5,0.149796 8.5,-8.5 0,-8.649796 -8.5,-8.5 -8.5,-8.5 h -20 v 20"
      />
    </svg>
  </div>
  <nav class={navOpen ? 'active' : ''}>
    <ul>
      <li class:active={$page.url.pathname === '/'}><a sveltekit:prefetch href="/">Home</a></li>
      <li class:active={$page.url.pathname === '/docs'}>
        <a sveltekit:prefetch href="/docs">Documentation</a>
      </li>
      <li class="nav-section-heading"><span>ABOUT</span></li>
      <li class:active={$page.url.pathname === '/docs/the-problem'}>
        <a sveltekit:prefetch href="/docs/the-problem">The Problem</a>
      </li>
      <li class:active={$page.url.pathname === '/docs/words-vs-patterns'}>
        <a sveltekit:prefetch href="/docs/words-vs-patterns">Words vs Patterns</a>
      </li>
      <li class:active={$page.url.pathname === '/docs/the-solution'}>
        <a sveltekit:prefetch href="/docs/the-solution">The Solution</a>
      </li>
      <li class="nav-section-heading"><span>GETTING STARTED</span></li>
      <li class:active={$page.url.pathname === '/docs/workflow-and-elements'}>
        <a sveltekit:prefetch href="/docs/workflow-and-elements">Workflow and Elements</a>
      </li>
      <li class:active={$page.url.pathname === '/docs/download-the-entropy-grid-generator'}>
        <a sveltekit:prefetch href="/docs/download-the-entropy-grid-generator"
          >Download the Entropy Grid Generator</a
        >
      </li>
      <li class:active={$page.url.pathname === '/docs/generating-entropy-grids'}>
        <a sveltekit:prefetch href="/docs/generating-entropy-grids">Generating Entropy Grids</a>
      </li>
      <li class:active={$page.url.pathname === '/docs/creating-a-border-wallet'}>
        <a sveltekit:prefetch href="/docs/creating-a-border-wallet">Creating a Border Wallet</a>
      </li>
      <li class:active={$page.url.pathname === '/docs/legacy-planning'}>
        <a sveltekit:prefetch href="/docs/legacy-planning">Legacy Planning</a>
      </li>
      <li class:active={$page.url.pathname === '/docs/best-practices'}>
        <a sveltekit:prefetch href="/docs/best-practices">Best Practices</a>
      </li>
      <li class:active={$page.url.pathname === '/docs/gotchas'}>
        <a sveltekit:prefetch href="/docs/gotchas">Gotchas</a>
      </li>
      <li class:active={$page.url.pathname === '/docs/bip39-seed-words'}>
        <a sveltekit:prefetch href="/docs/bip39-seed-words">BIP39 Seed Words</a>
      </li>
    </ul>
  </nav>
</header>

<style>
  header {
    display: flex;
    justify-content: space-between;
    background-color: var(--a-dark);
  }

  .corner {
    width: 7rem;
    height: 6rem;
    display: flex;
    justify-content: center;
  }

  .corner a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
  }

  .corner img {
    width: 6rem;
    height: 6rem;
    object-fit: contain;
    margin-left: 0.5em;
    fill: var(--a-light);
  }

  nav {
    /* display: flex;
    justify-content: center; */
    color: var(--a-light);
    background-color: var(--a-dark);
    position: fixed;
    left: 100vw;
    top: 6rem;
    width: 30rem;
    transition: 0.3s;
    overflow-y: scroll;
  }
  nav.active {
    left: calc(100vw - 30rem);
  }

  ul {
    position: relative;
    padding: 0;
    margin: 0;
    /* height: 3em; */
    /* display: flex; */
    justify-content: center;
    align-items: center;
    list-style: none;
    /* background: var(--background);
    background-size: contain; */
  }

  li {
    position: relative;
    padding: 1em 0 1em 0;
    /* height: 100%; */
  }

  /* li.active::before {
    --size: 6px;
    content: '';
    width: 0;
    height: 0;
    position: absolute;
    top: 0;
    left: calc(50% - var(--size));
    border: var(--size) solid transparent;
    border-top: var(--size) solid var(--accent-color);
  } */

  nav a {
    display: flex;
    height: 100%;
    align-items: center;
    padding: 0 1em;
    color: var(--a-light);
    font-weight: 700;
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    text-decoration: none;
    transition: color 0.2s linear;
  }

  .nav-section-heading {
    padding: 1rem;
    font-weight: 100;
    font-size: small;
    border-top: 1px solid var(--accent-color);
    display: block;
  }

  a:hover {
    color: var(--accent-color);
  }
  .ham {
    cursor: pointer;
    -webkit-tap-highlight-color: transparent;
    transition: transform 400ms;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }
  .hamRotate.active {
    transform: rotate(45deg);
  }
  .line {
    fill: none;
    transition: stroke-dasharray 400ms, stroke-dashoffset 400ms;
    stroke: var(--a-light);
    stroke-width: 5.5;
    stroke-linecap: round;
  }
  .ham4 .top {
    stroke-dasharray: 40 121;
  }
  .ham4 .bottom {
    stroke-dasharray: 40 121;
  }
  .ham4.active .top {
    stroke-dashoffset: -68px;
  }
  .ham4.active .bottom {
    stroke-dashoffset: -68px;
  }
  .ham4.active .line {
    stroke: var(--accent-color);
    transition: 0.3s;
  }
</style>
