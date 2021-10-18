<script>
  import Answer from "../shared/ui/Answer.svelte";

  import Btn from "../shared/ui/Btn.svelte";
  import Input from "../shared/ui/Input.svelte";
  import Select from "../shared/ui/Select.svelte";

  let amount = 865;
  let actual = 765;

  function percentOfNumber(amount, percent) {
    return ((amount / 100) * percent * 100) / 100;
  }

  function getPercentageChange(oldNumber, newNumber) {
    var decreaseValue = newNumber - oldNumber;

    return Math.round((decreaseValue / oldNumber) * 100);
  }
</script>

<p class="mb-4">Black Diamond</p>

<form>
  <div class="md:flex md:justify-between">
    <div class="w-full md:w-1/2 md:pr-4">
      <Input label="Amount" id="amount" bind:value="{amount}" type="number" />
    </div>
    <div class="w-full md:w-1/2 md:pr-2">
      <p>Target (% amount/total)</p>
      <p>
        1%: £{percentOfNumber(amount, 1).toFixed(2)}
        / £{(Number(percentOfNumber(amount, 1)) + Number(amount)).toFixed(2)}
      </p>
      <p>
        2%: £{percentOfNumber(amount, 2).toFixed(2)}
        / £{(Number(percentOfNumber(amount, 2)) + Number(amount)).toFixed(2)}
      </p>
      <p>
        3%: £{percentOfNumber(amount, 3).toFixed(2)}
        / £{(Number(percentOfNumber(amount, 3)) + Number(amount)).toFixed(2)}
      </p>
      <p>
        4%: £{percentOfNumber(amount, 4).toFixed(2)}
        / £{(Number(percentOfNumber(amount, 4)) + Number(amount)).toFixed(2)}
      </p>

      <p>
        £{Math.round(percentOfNumber(amount, 1))}-£{Math.round(percentOfNumber(amount, 4))}/£{Math.round(Number(percentOfNumber(amount, 1)) + Number(amount))}-£{Math.round(Number(percentOfNumber(amount, 4)) + Number(amount))}
      </p>
    </div>
  </div>
  <div class="md:flex md:justify-between mt-8">
    <div class="w-full md:w-1/2 md:pr-4">
      <Input label="Actual" id="actual" bind:value="{actual}" type="number" />
    </div>
    <div class="w-full md:w-1/2">
      <p>Actual (amount/total)</p>
      <p>
        Profit/loss: £{Math.round(actual - amount)}
        /
        {getPercentageChange(amount, actual)}%
      </p>
    </div>
  </div>
</form>
