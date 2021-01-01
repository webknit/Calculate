<script>
import Answer from "../shared/ui/Answer.svelte";
import Input from "../shared/ui/Input.svelte";

let age = 34;
let retirementAge = 65;
let personalMonthlyContribution = 150;
let employerMonthlyContribution = 150;

$: pensionTotal = calculateTotal();

function calculateTotal() {
  return 25;
  // (personalMonthlyContribution + employerMonthlyContribution) *
  //   12 *
  //   (retirementAge - age)
}
</script>

<p class="mb-4">
  Many people aim for a retirement income that’s two thirds of their current
  salary. For example, if your annual salary is currently £30,000, then £20,000
  per year would give you a reasonable retirement income. If you’re likely to be
  eligible for the full state pension (currently £9,110 per year 2021) then
  you’ll find an option to include this within the pension calculator.
</p>

<form>
  <div class="md:flex md:justify-between">
    <div class="w-full md:w-1/2 md:pr-2">
      <Input
        label="Current age"
        id="current-age"
        bind:value="{age}"
        type="number"
      />
      <Input
        label="Retirement age"
        id="retirement-age"
        bind:value="{retirementAge}"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/2 md:pl-2">
      <Input
        label="Personal monthly contribution"
        id="personal-cont"
        bind:value="{personalMonthlyContribution}"
        type="number"
      />
      <Input
        label="Employer monthly contribution"
        id="employer-cont"
        bind:value="{employerMonthlyContribution}"
        type="number"
      />
    </div>
  </div>
</form>

<Answer>
  <p>Pension pot: {pensionTotal}</p>
</Answer>
