<script>
  // @ts-nocheck

  import { page, getStores } from '$app/stores';
  import { slide } from 'svelte/transition';
  import { quintOut } from 'svelte/easing';
  import { browser } from '$app/env';
  import navList from './nav.json';

  const urlify = (text = '') => text.trim().toLowerCase().replaceAll(' ', '-');
  let navHeaders = Object.keys(navList);
  let navActive = {};
  navHeaders.forEach(
    (h) => (navActive[h] = !!navList[h].find((t = '') => urlify(t) === $page.url.pathname.slice(6)))
  );
  let navOpen = false;
  function toggleNav() {
    navOpen = !navOpen;
  }

  let isDark = false;
  if (browser) isDark = (localStorage.getItem('theme') ?? 'light') === 'dark';

  function switchTheme() {
    const themeDescription = isDark ? 'dark' : 'light';
    if (browser) {
      document.documentElement.setAttribute('data-theme', themeDescription);
      localStorage.setItem('theme', themeDescription);
    }
  }
  switchTheme();
</script>

<header>
  <div class="corner">
    <a href="/">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="logo"
        viewBox="0 0 270 150"
        xml:space="preserve"
      >
        <g>
          <path
            d="M0 7.738v13.818c0 5.157 2.578 7.737 7.738 7.737H79.04c4.235 0 6.446 2.396 6.446 7.003v7.738c0 4.238-1.842 6.446-5.711 6.446H7.738c-4.035 0-6.483 1.586-7.363 4.74L0 55.196v12.053c0 5.158 2.578 7.738 7.738 7.738h73.88c3.868 0 5.711 2.211 5.711 6.449v8.106c0 4.605-2.209 6.816-6.447 6.816H7.738c-5.16 0-7.738 2.58-7.738 7.738v14.188c0 5.157 2.578 7.737 7.738 7.737H100.962c5.715 0 8.662-2.58 8.662-7.923v-3.314c0-4.238 2.211-6.266 6.633-6.266h3.5c4.238 0 6.265-2.764 6.265-8.476V77.198c0-5.342-2.396-8.106-7.003-8.106h-4.238c-3.869 0-5.895-1.843-5.895-5.712v-3.684c0-3.869 2.025-5.712 5.895-5.712h2.211c4.607 0 7.004-2.396 7.004-7.371V27.637c0-6.08-2.58-9.026-7.738-9.026h-3.503c-4.235 0-6.446-2.211-6.446-6.634V9.029c0-6.08-3.318-9.029-9.949-9.029H7.738C2.578 0 0 2.58 0 7.738z"
          />
        </g>
        <g>
          <path
            d="M260.247 0h-13.818c-5.157 0-7.737 2.578-7.737 7.738V79.04c0 4.235-2.396 6.446-7.003 6.446h-7.738c-4.238 0-6.446-1.841-6.446-5.71V7.738c0-4.035-1.586-6.483-4.74-7.363L212.79 0h-12.053c-5.158 0-7.738 2.578-7.738 7.738v73.88c0 3.868-2.211 5.711-6.449 5.711h-8.106c-4.604 0-6.815-2.209-6.815-6.447V7.738c0-5.16-2.58-7.738-7.738-7.738h-14.188c-5.158 0-7.738 2.578-7.738 7.738V100.962c0 5.715 2.58 8.662 7.923 8.662h3.315c4.238 0 6.265 2.211 6.265 6.633v3.5c0 4.238 2.765 6.265 8.476 6.265h22.846c5.342 0 8.106-2.396 8.106-7.003v-4.238c0-3.869 1.843-5.895 5.712-5.895h3.684c3.869 0 5.712 2.025 5.712 5.895v2.211c0 4.607 2.396 7.004 7.371 7.004h18.977c6.08 0 9.026-2.58 9.026-7.738v-3.503c0-4.235 2.211-6.446 6.634-6.446h2.947c6.08 0 9.029-3.318 9.029-9.949V7.738C267.985 2.578 265.405 0 260.247 0z"
          />
        </g>
      </svg>
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
  {#if navOpen}
    <nav
      class={navOpen ? 'active' : ''}
      transition:slide={{ delay: 250, duration: 300, easing: quintOut }}
    >
      <ul>
        <li>
          <label class="theme-switch" for="checkbox">
            <input type="checkbox" id="checkbox" bind:checked={isDark} on:change={switchTheme} />
            <div class="slider round" />
          </label>
          {#if isDark}
            <span>DARK MODE ENABLED</span>
          {:else}
            <span>ENABLE DARK MODE</span>
          {/if}
        </li>
        <li class:active={$page.url.pathname === '/'}>
          <a on:click={toggleNav} sveltekit:prefetch href="/">Home</a>
        </li>
        <li class:active={$page.url.pathname === '/docs'}>
          <a on:click={toggleNav} sveltekit:prefetch href="/docs">Documentation</a>
        </li>
        {#each navHeaders as navHeader}
          <li class="nav-section-heading{navActive[navHeader] ? ' is-open' : ''}">
            <label
              ><input
                type="checkbox"
                bind:checked={navActive[navHeader]}
                style="display: none;"
              />{navHeader}</label
            >
          </li>
          {#if navActive[navHeader]}
            {#each navList[navHeader] as navItem}
              <li class:active={$page.url.pathname === '/docs/' + urlify(navItem)}>
                <a on:click={toggleNav} sveltekit:prefetch href="/docs/{urlify(navItem)}"
                  >{navItem}</a
                >
              </li>
            {/each}{/if}
        {/each}
      </ul>
    </nav>
  {/if}
</header>

<style>
  header {
    display: flex;
    justify-content: space-between;
    background-color: var(--header-bg-color);
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

  .corner svg {
    width: 6rem;
    height: 6rem;
    object-fit: contain;
    margin-left: 0.5em;
    fill: var(--accent-color);
  }

  nav {
    /* display: flex;
    justify-content: center; */
    color: var(--header-color);
    background-color: var(--header-bg-color);
    right: -200vw;
    top: 6rem;
    width: 30rem;
    max-width: 100vw;
    transition: 0.3s;
    display: none;
    position: absolute;
    z-index: 99;
  }
  nav.active {
    /* left: calc(100vw - 30rem); */
    right: 0;
    display: block;
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

  li.active {
    background-color: var(--accent-color);
  }

  li.active > a {
    color: var(--header-bg-color);
  }

  nav a {
    display: flex;
    height: 100%;
    align-items: center;
    padding: 0 1rem;
    color: var(--header-color);
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

  .nav-section-heading:before {
    content: '\02795'; /* Unicode character for "plus" sign (+) */
    font-size: 13px;
    color: var(--header-color);
    float: left;
    margin-right: 5px;
  }

  .is-open:before {
    content: '\2796'; /* Unicode character for "minus" sign (-) */
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
    stroke: var(--header-color);
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
  /* .theme-switch-wrapper {
    display: flex;
    align-items: center;
  } */

  nav > ul > li > span {
    margin-left: 10px;
    font-weight: 100;
    font-size: small;
  }

  .theme-switch {
    display: inline-block;
    height: 1rem;
    position: relative;
    width: 3rem;
  }

  .theme-switch input {
    display: none;
  }

  .slider {
    background-color: #888;
    bottom: 0;
    cursor: pointer;
    left: 1rem;
    position: absolute;
    right: 0;
    top: 0;
    transition: 0.4s;
  }

  .slider:before {
    background-color: var(--header-color);
    bottom: 0;
    content: '';
    height: 1rem;
    left: 0;
    position: absolute;
    transition: 0.4s;
    width: 1rem;
  }

  input:checked + .slider {
    background-color: var(--accent-color);
  }

  input:checked + .slider:before {
    transform: translateX(1rem);
  }

  .slider.round {
    border-radius: 34px;
  }

  .slider.round:before {
    border-radius: 50%;
  }
</style>
