<script>
  import { base } from '$app/paths';

  let {
    navLinks = [
      { label: 'Videos', href: `${base}/videos` },
      { label: 'About', href: `${base}/about` },
    ],
  } = $props();
</script>

<nav class="home-nav" aria-label="Main navigation">
  <ul class="nav-list">
    {#each navLinks as link (link.href)}
      <li><a href={link.href}>{link.label}</a></li>
    {/each}
  </ul>
</nav>

<style lang="scss">
  .home-nav {
    width: 100%;
    padding: var(--spacing-xs) var(--spacing-md);
    background: transparent;
  }

  .nav-list {
    display: flex;
    gap: var(--spacing-xxs);
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
    padding: 0.32rem 0.66rem;
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
  }
</style>
