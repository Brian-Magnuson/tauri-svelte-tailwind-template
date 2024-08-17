<script lang="ts">
  import { invoke } from "@tauri-apps/api/core";

  let response: string | undefined;

  const greet = async () => {
    response = await invoke("hello");
  };
</script>

<h1 class="text-4xl">Welcome to SvelteKit</h1>
<p>
  Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation
</p>

<button type="button" class="border-2 border-gray-700" on:click={() => greet()}>
  Click Me!
</button>

{#if response}
  <p>{response}</p>
{/if}
