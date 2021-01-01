<script>
import Answer from "../shared/ui/Answer.svelte";
import Input from "../shared/ui/Input.svelte";

let feet = 6;
let inches = 2;

// d(cm) = d(ft) × 30.48 + d(in) × 2.54
$: total = (feet * 30.48 + inches * 2.54).toFixed(2);
</script>

<form>
  <div class="md:flex">
    <div class="w-full md:w-1/2 md:pr-2">
      <Input label="Feet" id="amount-1" type="number" bind:value="{feet}" />
    </div>
    <div class="w-full md:w-1/2 md:px-2">
      <Input label="Inches" id="amount-1" type="number" bind:value="{inches}" />
    </div>
  </div>
</form>

<Answer value="{total} cm" />
