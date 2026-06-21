<script>
  import TextSection from '$lib/components/Content/TextSection.svelte';
  import Paragraph from '$lib/components/Content/Paragraph.svelte';
</script>

<svelte:head>
  <title>Stories | Tom & Evie</title>
  <meta name="description" content="Scaffold page for text stories and updates." />
</svelte:head>

<div class="container">
  <TextSection eyebrow="Stories" heading="Family Updates">
    {#snippet children()}
      <Paragraph text="This page now holds the text-first content for updates and milestones." />
      <Paragraph text="Add one section per story with as many paragraphs as you need." />
    {/snippet}
  </TextSection>

  <TextSection heading="Weekend Adventure">
    {#snippet children()}
      <Paragraph text="Tom and Evie spent the morning at the park and the afternoon building a cardboard spaceship." />
      <Paragraph text="Next weekend they want to add painted planets and a control panel with lots of buttons." />
    {/snippet}
  </TextSection>

  <TextSection heading="School and Hobbies">
    {#snippet children()}
      <Paragraph text="Evie has been drawing and making craft projects with stickers and glitter pens." />
      <Paragraph text="Tom has been talking about rockets, stars, and all the planets in order." />
    {/snippet}
  </TextSection>
</div>
