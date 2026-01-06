<script>
  export let title = 'Title';
  export let link = ''
  export let description = '';
</script>
<li>
  {#if link}
    <a href={link} target="_blank" rel="noopener">{title}</a>
  {:else}
    <span>{title}</span>
  {/if}
  <p>{@html description}</p>
</li>
