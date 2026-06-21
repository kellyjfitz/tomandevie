<script>
  let {
    title = 'Embedded video',
    src = 'https://www.youtube.com/embed/dQw4w9WgXcQ',
    caption = '',
    ratio = '16 / 9',
  } = $props();

  function toEmbedUrl(value) {
    if (!value) return '';

    const raw = String(value).trim();

    // Already an embed URL.
    if (raw.includes('youtube.com/embed/')) return raw;

    // Accept plain video IDs.
    if (/^[a-zA-Z0-9_-]{11}$/.test(raw)) {
      return `https://www.youtube.com/embed/${raw}`;
    }

    try {
      const url = new URL(raw);
      const host = url.hostname.replace(/^www\./, '');

      if (host === 'youtu.be') {
        const id = url.pathname.split('/').filter(Boolean)[0] ?? '';
        if (id) return `https://www.youtube.com/embed/${id}`;
      }

      if (host === 'youtube.com' || host === 'm.youtube.com') {
        const watchId = url.searchParams.get('v');
        if (watchId) return `https://www.youtube.com/embed/${watchId}`;

        const parts = url.pathname.split('/').filter(Boolean);
        const shortsIndex = parts.indexOf('shorts');
        if (shortsIndex >= 0 && parts[shortsIndex + 1]) {
          return `https://www.youtube.com/embed/${parts[shortsIndex + 1]}`;
        }
      }
    } catch {
      // Fall through to return raw when value is not a valid URL.
    }

    return raw;
  }

  const embedSrc = $derived(toEmbedUrl(src));
</script>

<section class="embed" aria-label={title}>
  <div class="frame" style:aspect-ratio={ratio}>
    <iframe
      title={title}
      src={embedSrc}
      loading="lazy"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin"
      allowfullscreen
    ></iframe>
  </div>
  {#if caption}
    <p class="caption">{caption}</p>
  {/if}
</section>

<style lang="scss">
  .embed {
    margin-top: var(--spacing-md);
  }

  .frame {
    width: 100%;
    background: var(--color-light-gray);
    border: var(--border-width-thin) solid var(--color-border);
    border-radius: var(--border-radius-sm);
    overflow: hidden;
    box-shadow: 0 8px 24px var(--color-shadow);
  }

  iframe {
    width: 100%;
    height: 100%;
    border: 0;
  }

  .caption {
    margin-top: var(--spacing-xs);
    color: var(--color-medium-gray);
    font-size: var(--font-size-sm);
  }
</style>
