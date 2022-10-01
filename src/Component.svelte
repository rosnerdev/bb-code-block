<script>
  import { getContext } from "svelte"
  import { HighlightAuto } from "svelte-highlight";
  import atom from "svelte-highlight/styles/atom-one-dark";
  import atomLight from "svelte-highlight/styles/atom-one-light";

  export let code
  export let theme

  const { styleable } = getContext("sdk")
  const component = getContext("component")
</script>

<svelte:head>
{#if theme == "Light"}  
  {@html atomLight}
{:else}
  {@html atom}
{/if}
</svelte:head>

<div use:styleable={$component.styles}>
  <HighlightAuto bind:code/>
</div>
