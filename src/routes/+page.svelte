<script>
  import { base } from '$app/paths';

  const pageTitle = 'Tom & Evie';
</script>

<svelte:head>
  <title>{pageTitle}</title>
  <meta
    name="description"
    content="Tom and Evie home page with featured video and links to more pages."
  />
</svelte:head>

<section class="home-banner">
  <img
    src="{base}/tom_evie_banner.png"
    alt="Tom and Evie"
    width="1600"
    height="420"
  />
</section>

<style lang="scss">
  .home-banner {
    width: 100%;
    display: flex;
    justify-content: center;
  }

  .home-banner img {
    width: min(100%, 1280px);
    margin: 0;
    display: block;
  }
</style>
