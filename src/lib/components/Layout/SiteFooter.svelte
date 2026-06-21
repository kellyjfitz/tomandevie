<script>
  import { base } from '$app/paths';

  let {
    siteTitle = 'Tom & Evie',
    home = false,
    note = 'Videos and stories',
    links = [
      { label: 'Home', href: `${base}/` },
      { label: 'Videos', href: `${base}/videos` },
      { label: 'About', href: `${base}/about` },
    ],
  } = $props();

  const year = new Date().getFullYear();
</script>

<footer class="site-footer" class:no-top-gap={home} class:home-footer={home}>
  <div class="container footer-inner">
    <div>
      <h2>{siteTitle}</h2>
      <p>{note}</p>
    </div>

    {#if links.length > 0}
      <nav aria-label="Footer navigation">
        <ul>
          {#each links as link (link.href)}
            <li><a href={link.href}>{link.label}</a></li>
          {/each}
        </ul>
      </nav>
    {/if}
  </div>
  <p class="copyright">&copy; {year} {siteTitle}</p>
</footer>

<style lang="scss">
  .site-footer {
    margin-top: var(--spacing-xxl);
    border-top: 0;
    background: linear-gradient(
      120deg,
      var(--color-brand-blue-dark),
      var(--color-brand-blue-light)
    );
    padding: var(--spacing-lg) 0 var(--spacing-sm);
  }

  .site-footer.no-top-gap {
    margin-top: 0;
  }

  .site-footer.home-footer {
    background: transparent;
  }

  .footer-inner {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--spacing-md);
  }

  h2 {
    margin: 0 0 var(--spacing-xs);
    font-size: var(--font-size-xl);
    color: var(--color-white);
  }

  p {
    margin: 0;
    color: color-mix(in srgb, var(--color-white) 82%, transparent);
  }

  ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    gap: var(--spacing-sm);
    flex-wrap: wrap;
  }

  a {
    text-decoration: none;
    color: var(--color-white);
    font-weight: var(--font-weight-semibold);
    font-size: var(--font-size-sm);
    padding: 0.18rem 0.45rem;
    border-radius: 999px;
  }

  a:hover {
    color: var(--color-white);
    background: color-mix(in srgb, var(--color-white) 16%, transparent);
  }

  .copyright {
    margin-top: var(--spacing-md);
    text-align: center;
    font-size: var(--font-size-sm);
    color: color-mix(in srgb, var(--color-white) 78%, transparent);
  }

  @media (min-width: 768px) {
    .footer-inner {
      grid-template-columns: 1fr auto;
      align-items: end;
    }
  }
</style>
