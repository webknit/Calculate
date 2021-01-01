<script>
import Answer from "../shared/ui/Answer.svelte";
import Input from "../shared/ui/Input.svelte";
import Select from "../shared/ui/Select.svelte";

export let unit1, unit2, amount1, units, sums;

console.log();

$: total = (amount1 * sums[unit1][unit2]).toFixed(2);
</script>

<form>
  <div class="md:flex">
    <div class="w-full md:w-1/3 md:pr-2">
      <Input
        label="Amount 1"
        id="amount-1"
        type="number"
        bind:value="{amount1}"
      />
    </div>
    <div class="w-full md:w-1/3 md:px-2">
      <Select
        label="Unit 1"
        id="unit-1"
        bind:value="{unit1}"
        options="{units}"
        disabled="{unit2}"
      />
    </div>
    <div class="w-full md:w-1/3 md:pl-2">
      <Select
        label="Unit 2"
        id="unit-2"
        bind:value="{unit2}"
        options="{units}"
        disabled="{unit1}"
      />
    </div>
  </div>
</form>

<Answer value="{total} {unit2}" />
