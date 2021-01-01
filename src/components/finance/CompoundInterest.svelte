<script>
import Btn from "../shared/ui/btn.svelte";
import Input from "../shared/ui/Input.svelte";

let initialAmount = 0;
let interest = 0;
let duration = 0;

const onFormSubmit = () => {
  console.log(
    calculateCompountInterestTotal(initialAmount, duration, interest, 12)
  );
};

function calculateCompountInterestTotal(p, t, r, n) {
  const amount = p * Math.pow(1 + r / (n * 100), n * t);
  const interest = amount - p;
  return interest;
}
</script>

<form on:submit|preventDefault="{onFormSubmit}">
  <div class="md:flex md:justify-between">
    <div class="w-full md:w-1/3 pr-2">
      <Input
        label="Initial amount"
        id="initialAmount"
        bind:value="{initialAmount}"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/3 px-2">
      <Input
        label="Interest rate (%)"
        id="interest"
        bind:value="{interest}"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/3 pl-2">
      <Input
        label="Duration (years)"
        id="duration"
        bind:value="{duration}"
        type="number"
      />
    </div>
  </div>

  <Btn />
</form>

<hr />

<div class="mt-4">
  <ul>
    Initial amount
    {initialAmount}
    <!-- <li>Total: {{ compountInterestTotal }}</li> -->
  </ul>
</div>
