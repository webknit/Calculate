<script>
import Btn from "../components/shared/ui/btn.svelte";
import Input from "../components/shared/ui/Input.svelte";

let initialAmount = 0;
let interest = 0;
let duration = 0;

const onFormSubmit = () => {
  console.log("hello");
};
</script>

<h1 class="text-3xl font-extrabold text-gray-900 mb-4">Compound Interest</h1>

<form class="mb-4" on:submit|preventDefault="{onFormSubmit}">
  <div class="md:flex md:justify-between mb-4">
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
