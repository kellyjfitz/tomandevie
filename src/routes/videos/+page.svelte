<script>
  import EmbedVideo from '$lib/components/Content/EmbedVideo.svelte';
  import TextSection from '$lib/components/Content/TextSection.svelte';
  import Paragraph from '$lib/components/Content/Paragraph.svelte';
  let {data} = $props();
</script>

<svelte:head>
  <title>Videos | Tom & Evie</title>
  <meta name="description" content="Embedded videos." />
</svelte:head>

<div class="container">
  <TextSection heading="Watch our videos">
    {#snippet children()}
      <Paragraph text="Take a look at some of the things we get up to." />
      
    {/snippet}
  </TextSection>

    {#each data.videos as video }
        <EmbedVideo title={video.title} src={video.src}/>
    {/each}

</div>
