<script lang="ts">
    import { createDialog, melt } from '@melt-ui/svelte'
    const {
      elements: { trigger, portalled, overlay, content, title, description, close },
      states: { open }
    } = createDialog()
  </script>
   
  <button use:melt={$trigger}> Open Dialog </button>
   
  <div use:melt={$portalled}>
    {#if $open}
      <div use:melt={$overlay} />
      <div use:melt={$content}>
        <h2 use:melt={$title}>Dialog Title</h2>
        <p use:melt={$description}>Dialog description</p>
        <button use:melt={$close}> Close Dialog </button>
      </div>
    {/if}
  </div>