<script>
import PageNav from "../components/shared/partials/PageNav.svelte";
import PageTitle from "../components/shared/ui/PageTitle.svelte";
import { pages } from "../PagesComponentsList.svelte";

export let filterID = "";
export let title = "";

const filter = pages.find(i => i.id == filterID);
</script>

<PageTitle title="{title}" />

<PageNav items="{filter.components}" />

{#each filter.components as { id, name, component, unit1, unit2, amount1, units, sums }, i}
  <div id="{id}" class="my-8">
    <h2 class="text-2xl font-extrabold text-gray-900 mb-4">{name}</h2>
    <svelte:component
      this="{component}"
      unit1="{unit1}"
      unit2="{unit2}"
      amount1="{amount1}"
      units="{units}"
      sums="{sums}"
    />
  </div>
  {#if i !== filter.components.length - 1}
    <hr class="mt-4" />
  {/if}
{/each}
