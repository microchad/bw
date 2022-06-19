<script>
  export let previous = '';
  export let next = '';
  export let pageNo = 0;
</script>

<slot />

<div class="controls">
  <div class="prev">
    {#if previous}
      <span>PREVIOUS</span>
      <a
        href="/docs/{previous === 'Start'
          ? ''
          : `${(pageNo - 1).toString().padStart(2, '0')}_` +
            previous.trim().toLowerCase().replaceAll(' ', '-')}">{previous}</a
      >
    {/if}
  </div>
  <div class="next">
    {#if next}
      <span>NEXT</span>
      <a
        href="/docs/{`${(pageNo + 1).toString().padStart(2, '0')}_` +
          next.trim().toLowerCase().replaceAll(' ', '-')}">{next}</a
      >
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
