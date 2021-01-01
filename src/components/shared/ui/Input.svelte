<script>
import { createEventDispatcher } from "svelte";
const dispatch = createEventDispatcher();
export let value, id, label, type;
function typeAction(node) {
  node.type = type || "text";
}
const onKeyup = () => dispatch("onKeyup");
</script>

<div class="mb-4">
  <label for="{id}">{label}</label>
  <input
    class="border-gray-400 border-solid border p-2 w-full"
    id="{id}"
    bind:value
    use:typeAction
    on:keyup="{onKeyup}"
  />
</div>
