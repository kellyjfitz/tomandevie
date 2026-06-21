<script>
  let {
    eyebrow = '',
    heading = '',
    text = '',
    children,
  } = $props();
</script>

<section class="text-section">
  {#if eyebrow}
    <p class="eyebrow">{eyebrow}</p>
  {/if}
  {#if heading}
    <h2>{heading}</h2>
  {/if}
  {#if children}
    <div class="body">
      {@render children()}
    </div>
  {:else if text}
    <p class="body-paragraph">{text}</p>
  {/if}
</section>

<style lang="scss">
  .text-section {
    margin-top: var(--spacing-lg);
  }

  .eyebrow {
    margin-bottom: var(--spacing-xxs);
    text-transform: uppercase;
    letter-spacing: var(--letter-spacing-wider);
    color: var(--color-accent);
    font-size: var(--font-size-sm);
    font-weight: var(--font-weight-bold);
  }

  h2 {
    margin-bottom: var(--spacing-xs);
  }

  .body-paragraph,
  .body :global(p),
  .body :global(.text-paragraph) {
    max-width: 70ch;
    color: var(--color-text);
    margin-bottom: var(--spacing-sm);
  }

  .body :global(p:last-child),
  .body :global(.text-paragraph:last-child) {
    margin-bottom: 0;
  }
</style>
