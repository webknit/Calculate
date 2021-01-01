<script>
export let items;
</script>

{#each items as { id, name }, i}
  <nav class="flex mb-8">
    <a
      class="border-gray-300 border-solid border-r pr-4"
      href="#{id}"
    >{name}</a>
  </nav>
{/each}
