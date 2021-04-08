<script>
import Answer from "../shared/ui/Answer.svelte";

import Btn from "../shared/ui/Btn.svelte";
import Input from "../shared/ui/Input.svelte";
import Select from "../shared/ui/Select.svelte";

let backStake = 20;
let backOdds = 1.55;
let layOdds = 1.33;
let commission = 2;

$: hedgingCalculation = (backOdds * backStake) / layOdds;
$: liability =  hedgingCalculation * (layOdds - 1);
$: profit =  ((backStake * backOdds) - (liability)) - backStake;

function twoDecimal(num) {
    return Math.round(num * 100) / 100;
}

</script>

<p class="mb-4">Matched betting</p>

<form>
  <div class="md:flex md:justify-between">
    <div class="w-full md:w-1/2 md:pr-2">
      <Input
        label="Back stake"
        id="backStake"
        bind:value="{backStake}"
        type="number"
      />
      <Input
        label="Back odds"
        id="back-odds"
        bind:value="{backOdds}"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/2 md:px-2">
      <Input
        label="Lay odds "
        id="layOdds"
        bind:value="{layOdds}"
        type="number"
      />
      <!-- <Input
        label="Commission"
        id="commission"
        bind:value="{commission}"
        type="number"
      /> -->
    </div>
  </div>
</form>

<p>Your lay stake is : <strong>{twoDecimal(hedgingCalculation)}</strong></p>
<p>Liability: <strong>{twoDecimal(liability)}</strong></p>
<!-- <p>Exchange balance required is: {liability}</p> -->
<p>Profit: <strong>{twoDecimal(profit)}</strong></p>

