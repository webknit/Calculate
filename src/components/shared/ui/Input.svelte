<script>
import { createEventDispatcher } from "svelte";
const dispatch = createEventDispatcher();
export let value, id, label, type;
function typeAction(node) {
  node.type = type || "text";
}
</script>

<label for="{id}">{label}</label>
<input
  class="border-gray-400 border-solid border p-2 w-full"
  id="{id}"
  bind:value
  use:typeAction
/>
