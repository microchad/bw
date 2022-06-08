<script>
  export let previous = '';
  export let next = '';
</script>

<slot />

<div class="controls">
  <div class="prev">
    {#if previous}
      <span>PREVIOUS</span>
      <a
        href="/docs/{previous === 'start'
          ? ''
          : previous.trim().toLowerCase().replaceAll(' ', '-')}">{previous}</a
      >
    {/if}
  </div>
  <div class="next">
    {#if next}
      <span>NEXT</span>
      <a href="/docs/{next.trim().toLowerCase().replaceAll(' ', '-')}">{next}</a>
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
