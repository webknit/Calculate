<script>
export let buttonAction = () => console.log("No action passsed");
export let type = "submit";
</script>

<button type="{type}" class="border-gray-400" on:click="{buttonAction}">Click me</button>
