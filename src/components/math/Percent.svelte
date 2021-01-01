<script>
import Answer from "../shared/ui/Answer.svelte";
import Input from "../shared/ui/Input.svelte";

let percent = 50;
let number = 27568;
$: percentOfNumber = Math.round((number / 100) * percent);
</script>

<form>
  <div class="md:flex items-end">
    <div class="w-full md:w-1/2 md:pr-2">
      <Input
        label="Percent %"
        id="percent"
        bind:value="{percent}"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/2 md:pl-2">
      <Input label="Number" id="number" bind:value="{number}" type="number" />
    </div>
  </div>
</form>

<Answer value="{percentOfNumber}" />
