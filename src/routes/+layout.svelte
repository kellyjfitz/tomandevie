<script>
  import '../app.scss';
  import { base } from '$app/paths';
  import { page } from '$app/state';
  import HomeNav from '$lib/components/Layout/HomeNav.svelte';
  import SiteHeader from '$lib/components/Layout/SiteHeader.svelte';
  import SiteFooter from '$lib/components/Layout/SiteFooter.svelte';

  let { children } = $props();

  const isHome = $derived(
    page.url.pathname === `${base}/` || page.url.pathname === base
  );
</script>

{#if isHome}
  <div class="home-shell">
    <HomeNav />
    <main class="home-main">
      {@render children()}
    </main>
    <SiteFooter home={true} />
  </div>
{:else}
  <SiteHeader />
  <main>
    {@render children()}
  </main>
  <SiteFooter />
{/if}

<style>
  main {
    min-height: 100vh;
  }

  .home-shell {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    background: linear-gradient(
      120deg,
      var(--color-brand-blue-dark),
      var(--color-brand-blue-light)
    );
  }

  .home-main {
    background: transparent;
    min-height: 0;
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
