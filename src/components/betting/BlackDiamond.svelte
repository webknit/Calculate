<script>
  import Answer from "../shared/ui/Answer.svelte";

  import Btn from "../shared/ui/Btn.svelte";
  import Input from "../shared/ui/Input.svelte";
  import Select from "../shared/ui/Select.svelte";

  let amount = 765;
  let actual = 765;

  function percentOfNumber(amount, percent) {
    return Math.round((amount / 100) * percent * 100) / 100;
  }

  function relDiff(a, b) {
    // (current-new)/current*100.0;
    return Math.round(((a - b) / a) * 100.0);
  }

  function getPercentageChange(oldNumber, newNumber) {
    var decreaseValue = newNumber - oldNumber;

    return Math.round((decreaseValue / oldNumber) * 100);
  }

  //   $: hedgingCalculation = (backOdds * backStake) / layOdds;
  //   $: liability = hedgingCalculation * (layOdds - 1);
  //   $: profit = backStake * backOdds - liability - backStake;

  function twoDecimal(num) {
    return Math.round(num * 100) / 100;
  }
</script>

<p class="mb-4">Black Diamond</p>

<form>
  <div class="md:flex md:justify-between">
    <div class="w-full md:w-1/2 md:pr-4">
      <Input label="Amount" id="amount" bind:value="{amount}" type="number" />
    </div>
    <div class="w-full md:w-1/2 md:pr-2">
      <p>Target (%/total)</p>
      <p>
        1% - £{percentOfNumber(amount, 1)}
        / £{percentOfNumber(amount, 1) + amount}
      </p>
      <p>
        2% - £{percentOfNumber(amount, 2)}
        / £{percentOfNumber(amount, 2) + amount}
      </p>
      <p>
        3% - £{percentOfNumber(amount, 3)}
        / £{percentOfNumber(amount, 3) + amount}
      </p>
      <p>
        4% - £{percentOfNumber(amount, 4)}
        / £{percentOfNumber(amount, 4) + amount}
      </p>
    </div>
  </div>
  <div class="md:flex md:justify-between mt-8">
    <div class="w-full md:w-1/2 md:pr-4">
      <Input label="Actual" id="actual" bind:value="{actual}" type="number" />
    </div>
    <div class="w-full md:w-1/2">
      <p>Target (%/total)</p>
      <p>
        Profit/loss - £{Math.round(actual - amount)}
        /
        {getPercentageChange(amount, actual)}%
      </p>
    </div>
  </div>
</form>

<!-- <p>Your lay stake is : <strong>{twoDecimal(hedgingCalculation)}</strong></p>
<p>Liability: <strong>{twoDecimal(liability)}</strong></p>
 <p>Exchange balance required is: {liability}</p> 
<p>Profit: <strong>{twoDecimal(profit)}</strong></p>
-->
