<script>
  import { base } from '$app/paths';

  let {
    siteTitle = 'Tom & Evie',
    navLinks = [
      { label: 'Home', href: `${base}/` },
      { label: 'Videos', href: `${base}/videos` },
      { label: 'About', href: `${base}/about` },
    ],
  } = $props();
</script>

<header class="site-header">
  <section class="inner-bar">
    <a class="brand" href="{base}/" aria-label="{siteTitle} home page">
      <img
        class="inner-icon"
        src="{base}/tom_evie_icon.png"
        alt="{siteTitle} logo"
        width="90"
      />
    </a>

    {#if navLinks.length > 0}
      <nav aria-label="Main navigation">
        <ul class="nav-list">
          {#each navLinks as link (link.href)}
            <li><a href={link.href}>{link.label}</a></li>
          {/each}
        </ul>
      </nav>
    {/if}
  </section>
</header>

<style lang="scss">
  .site-header {
    background: var(--color-white);
    border-bottom: var(--border-width-thin) solid var(--color-border);
  }

  .inner-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: var(--spacing-xs);
    padding-top: 0.42rem;
    padding-bottom: 0.42rem;
    padding-left: var(--spacing-sm);
    padding-right: var(--spacing-sm);
    background: linear-gradient(
      120deg,
      var(--color-brand-blue-dark),
      var(--color-brand-blue-light)
    );
    border-bottom: 0;
  }

  .brand {
    color: var(--color-dark);
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: var(--spacing-xs);
  }

  .brand img {
    display: block;
  }

  .inner-icon {
    width: 72px;
    height: auto;
    max-width: none;
    flex: 0 0 auto;
  }

  .brand-text {
    display: flex;
    flex-direction: column;
    line-height: 1.1;
  }

  .brand-kicker,
  .brand-title {
    white-space: nowrap;
  }

  .brand-kicker {
    color: var(--color-accent);
    text-transform: uppercase;
    letter-spacing: var(--letter-spacing-wider);
    font-size: var(--font-size-xs);
    font-weight: var(--font-weight-bold);
  }

  .brand-title {
    font-size: var(--font-size-xl);
    font-weight: var(--font-weight-bold);
  }

  .nav-list {
    display: flex;
    gap: 0;
    list-style: none;
    margin: 0;
    padding: 0;
    flex-wrap: wrap;
    justify-content: flex-end;
    align-items: center;
  }

  .nav-list a {
    color: var(--color-white);
    text-decoration: none;
    font-size: 0.92rem;
    font-weight: var(--font-weight-bold);
    letter-spacing: 0.01em;
    padding: 0.36rem 0.7rem;
    border-radius: 999px;
    line-height: 1.2;
  }

  .nav-list a:hover {
    color: var(--color-white);
    background: color-mix(in srgb, var(--color-white) 16%, transparent);
  }

  @media (max-width: 700px) {
    .nav-list {
      justify-content: flex-start;
    }

    .inner-bar {
      gap: var(--spacing-xs);
      padding-left: var(--spacing-xs);
      padding-right: var(--spacing-xs);
    }
  }
</style>
