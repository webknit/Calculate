<script>
export let buttonAction = () => console.log("No action passsed");
export let type = "submit";
</script>

<button
  type="{type}"
  class="p-2 text-white rounded-lg bg-blue-600 text-white hover:bg-blue-800"
  on:click="{buttonAction}"
>Click me</button>
