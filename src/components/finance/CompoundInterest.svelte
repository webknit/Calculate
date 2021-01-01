<script>
import Answer from "../shared/ui/Answer.svelte";

import Btn from "../shared/ui/Btn.svelte";
import Input from "../shared/ui/Input.svelte";
import Select from "../shared/ui/Select.svelte";

let initialAmount = 1000;
let interest = 5;
let duration = 20;
let compound = 12;
let annualAddition = 500;

$: compountInterestTotal = calculateCompountInterestTotal(
  initialAmount + annualAddition * duration,
  duration,
  interest,
  compound
).toFixed(2);

function calculateCompountInterestTotal(p, t, r, n) {
  const amount = p * Math.pow(1 + r / (n * 100), n * t);
  const interest = amount - p;
  return interest;
}
</script>

<p class="mb-4">Interest compounds monthly (12 times a year).</p>

<form>
  <div class="md:flex md:justify-between">
    <div class="w-full md:w-1/3 md:pr-2">
      <Input
        label="Initial amount"
        id="initialAmount"
        bind:value="{initialAmount}"
        type="number"
      />
      <Input
        label="Annual Addition"
        id="annual-addition"
        bind:value="{annualAddition}"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/3 md:px-2">
      <Input
        label="Interest rate (%)"
        id="interest"
        bind:value="{interest}"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/3 md:pl-2">
      <Input
        label="Duration (years)"
        id="duration"
        bind:value="{duration}"
        type="number"
      />
      <Select
        label="Compount (times per year)"
        id="compound"
        bind:value="{compound}"
        options="{[12, 6, 4, 2, 1]}"
      />
    </div>
  </div>
</form>

<Answer>
  <p>Total: {compountInterestTotal}</p>
</Answer>
