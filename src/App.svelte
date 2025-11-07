<script lang="ts">
import { invoke } from "@tauri-apps/api/core";

let greetMsg = $state("");
// biome-ignore lint/style/useConst: Svelte reactive state
let name = $state("");

async function greet() {
  greetMsg = await invoke("greet", { name });
}
</script>

<main class="container mx-auto p-8">
  <h1 class="text-4xl font-bold mb-8 text-blue-600">Welcome to Tauri + Svelte 5!</h1>

  <div class="max-w-md mx-auto space-y-4">
    <div class="flex gap-2">
      <input
        id="greet-input"
        class="flex-1 px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
        placeholder="Enter a name..."
        bind:value={name}
      />
      <button
        type="button"
        class="px-6 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition-colors"
        onclick={greet}
      >
        Greet
      </button>
    </div>

    {#if greetMsg}
      <p class="text-lg font-semibold text-green-600">{greetMsg}</p>
    {/if}
  </div>

  <div class="mt-12">
    <p class="text-gray-600">
      Click the button to interact with the Tauri backend!
    </p>
  </div>
</main>
