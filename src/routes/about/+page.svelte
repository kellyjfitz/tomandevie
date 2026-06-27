<script>
  import TextSection from '$lib/components/Content/TextSection.svelte';
  import Paragraph from '$lib/components/Content/Paragraph.svelte';
  import Image from '$lib/components/Media/Image.svelte';
  
</script>

<svelte:head>
  <title>About | Tom & Evie</title>
  <meta name="description" content="About page for the Tom and Evie site." />
</svelte:head>

<div class="container">
  <TextSection heading="About Tom and Evie">
    {#snippet children()}
      <Paragraph text="Tom and Evie are siblings who live in Australia." />
      <Paragraph
        text="Evie is almost eight and likes craft, sushi, stuffed animals and puzzles."
      />
      <Paragraph
        text="Tom is six and enjoys hot chips, playing games and talking about space (a lot)."
      />
    {/snippet}
  </TextSection>

  <Image src="/tom_evie_square.png" alt="Tom and Evie logo" />
</div>
