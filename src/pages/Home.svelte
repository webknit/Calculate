<script>
import PageTitle from "../components/shared/ui/PageTitle.svelte";
import { pages } from "../PagesComponentsList.svelte";

const items = pages.filter(i => i.id !== "home");

console.log(items);
</script>

<PageTitle title="Home" />

{#each items as item}
  <div class="mt-8">
    <h2 class="text-2xl font-extrabold text-gray-900 mt-4">{item.name}</h2>
    {#each item.components as component}
      <a
        href="{item.path}#{component.id}"
        class="hover:underline block"
      >{component.name}</a>
    {/each}
  </div>
{/each}
