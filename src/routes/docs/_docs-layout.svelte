<script>
  import { page } from '$app/stores';
  import navList from '../../lib/header/nav.json';
  import { urlify } from '../../lib/urlify';
  /**
   * @type {string[]} pageList
   */
  // @ts-ignore
  let pageList = Object.keys(navList)
    // @ts-ignore
    .map((h = '') => navList[h])
    .flat();
  pageList.unshift('Start');
  let pageIndex = pageList.findIndex((t = '') => urlify(t) === $page.url.pathname.slice(6));
  pageIndex = pageIndex < 0 ? 0 : pageIndex;
  export let currentPage = pageList[pageIndex];
  export let previousPage = pageIndex === 0 ? '' : pageList[pageIndex - 1];
  export let nextPage = pageIndex >= pageList.length - 1 ? '' : pageList[pageIndex + 1];
</script>

<svelte:head>
  <!-- Primary Meta Tags -->
  <title>Border Wallets Documentation - {currentPage}</title>
  <meta name="title" content="Border Wallets Documentation - {currentPage}" />
  <meta
    name="description"
    content="Memorising Bitcoin seed phrases is now significantly easier with user-generated patterns & no sacrificed entropy. By exploiting a phenomenon known as the Picture Superiority Effect"
  />

  <!-- Open Graph / Facebook -->
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://www.borderwallets.com/" />
  <meta property="og:title" content="Border Wallets Documentation - {currentPage}" />
  <meta
    property="og:description"
    content="Memorising Bitcoin seed phrases is now significantly easier with user-generated patterns & no sacrificed entropy. By exploiting a phenomenon known as the Picture Superiority Effect"
  />
  <meta property="og:image" content="/BorderWallets.png" />

  <!-- Twitter -->
  <meta property="twitter:card" content="summary_large_image" />
  <meta property="twitter:url" content="https://www.borderwallets.com/" />
  <meta property="twitter:title" content="Border Wallets Documentation - {currentPage}" />
  <meta
    property="twitter:description"
    content="Memorising Bitcoin seed phrases is now significantly easier with user-generated patterns & no sacrificed entropy. By exploiting a phenomenon known as the Picture Superiority Effect"
  />
  <meta property="twitter:image" content="/{urlify(currentPage)}.png" />
</svelte:head>

<slot />

<div class="controls">
  <div class="prev">
    {#if previousPage}
      <span>PREVIOUS</span>
      <a
        href="/docs/{previousPage === 'Start'
          ? ''
          : previousPage.trim().toLowerCase().replaceAll(' ', '-')}">{previousPage}</a
      >
    {/if}
  </div>
  <div class="next">
    {#if nextPage}
      <span>NEXT</span>
      <a href="/docs/{nextPage.trim().toLowerCase().replaceAll(' ', '-')}">{nextPage}</a>
    {/if}
  </div>
</div>

<style>
  .prev {
    text-align: left;
  }
  .next {
    text-align: right;
  }
  .prev > span,
  .next > span {
    display: block;
    font-size: 0.75rem;
    font-weight: 600;
  }
  .prev > a,
  .next > a {
    font-weight: 900;
    font-size: 1.3rem;
  }
  .controls {
    max-width: 73em;
    /* border: 1px solid var(--primary-color); */
    border-radius: 0.5rem;
    background-color: var(--header-bg-color);
    padding: 1rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin: 6rem 0 0;
  }
</style>
