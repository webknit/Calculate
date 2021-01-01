<script>
import { createEventDispatcher } from "svelte";
const dispatch = createEventDispatcher();
export let value, id, label, options, disabled;
</script>

<div class="mb-4">
  <label for="{id}">{label}</label>
  <select
    id="{id}"
    bind:value
    class="border-gray-400 border-solid border p-2 w-full"
  >
    {#each options as option}
      {#if option == disabled}
        <option value="{option}" disabled>{option}</option>
      {:else}
        <option value="{option}">{option}</option>
      {/if}
    {/each}
  </select>
</div>
