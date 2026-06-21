<script>
  let { text = '' } = $props();
</script>

<p class="text-paragraph">
  {#if text}{text}{:else}<slot />{/if}
</p>

<style>
  .text-paragraph {
    max-width: 70ch;
    color: var(--color-text);
    margin-bottom: var(--spacing-sm);
  }
</style>
