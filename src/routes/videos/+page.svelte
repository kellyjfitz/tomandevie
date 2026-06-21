<script>
  import EmbedVideo from '$lib/components/Content/EmbedVideo.svelte';
  import TextSection from '$lib/components/Content/TextSection.svelte';
  import Paragraph from '$lib/components/Content/Paragraph.svelte';
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

  <EmbedVideo
    title="Puzzle time"
    src="https://youtu.be/g39tfyZ0nMw"
  />

  <EmbedVideo
    title="Tom explains the solar system"
    src="https://youtu.be/iTS4LjgsKkY"
  />
</div>
