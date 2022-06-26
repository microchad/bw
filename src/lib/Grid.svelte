<script>
  export let tableData = [
    [
      {
        word: '',
        pattern: 'is-hidden'
      }
    ]
  ];
</script>

<table>
  <tbody>
    {#each Object.values(tableData) as row}
      <tr>
        {#each Object.values(row) as cell}
          <td class={cell.pattern}>{cell.word}</td>
        {/each}
      </tr>
    {/each}
  </tbody>
</table>

<style>
  table {
    border-collapse: collapse;
    width: 100%;
    margin: 0 auto;
  }
  td {
    border: 1px solid var(--secondary-color);
    color: var(--secondary-color);
    text-align: center;
    vertical-align: middle;
  }
  td.is-pattern {
    background-color: var(--accent-color);
    color: var(--header-bg-color);
  }
  td.is-hidden {
    background-color: var(--bg-color);
    color: var(--bg-color);
    border: none;
  }
</style>
