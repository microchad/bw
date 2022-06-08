<script>
  export let previous = '';
  export let next = '';
</script>

<slot />

<div class="controls">
  <div class="prev">
    {#if previous}
      <span>PREVIOUS</span>
      <a href="/docs/{previous === 'start' ? 'index' : previous}"
        >{previous.slice(0, 1).toUpperCase() + previous.slice(1)}</a
      >
    {/if}
  </div>
  <div class="next">
    {#if next}
      <span>NEXT</span>
      <a href="/docs/{next}"
        >{next
          .split('-')
          .map((w) => `${w.slice(0, 1).toUpperCase()}${w.slice(1)}`)
          .join(' ')}</a
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
  }
  .controls {
    max-width: 73em;
    border-top: 1px solid var(--a-dark);
    padding: 1rem 0 0;
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin: 6rem 0 0;
  }
</style>
