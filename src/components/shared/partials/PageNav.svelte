<script>
export let items;
</script>

<nav class="flex mb-8">
  {#each items as { id, name }, i}
    <a
      class="border-gray-300 border-solid border-r pr-4 mr-4 hover:underline text-light-blue-600"
      href="#{id}"
    >{name}</a>
  {/each}
</nav>
