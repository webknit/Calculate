<h1 class="text-3xl font-extrabold text-gray-900 mb-4">Compound Interest</h1>

<form class="mb-4">
  <div class="md:flex md:justify-between mb-4">
    <div class="w-full md:w-1/3 pr-2">
      <label for="initialAmount">Initial amount</label>
      <input
        class="border-gray-400 border-solid border p-2 w-full"
        id="initialAmount"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/3 px-2">
      <label for="interest">Interest rate (%)</label>
      <input
        class="border-gray-400 border-solid border p-2 w-full"
        id="interest"
        type="number"
      />
    </div>
    <div class="w-full md:w-1/3 pl-2">
      <label for="duration">Duation (years)</label>
      <input
        class="border-gray-400 border-solid border p-2 w-full"
        id="duration"
        type="number"
      />
    </div>
  </div>

  <input type="submit" />
</form>

<hr />

<div class="mt-4">
  <ul>
    <!-- <li>Total: {{ compountInterestTotal }}</li> -->
  </ul>
</div>
