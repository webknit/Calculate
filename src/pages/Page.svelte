<script>
import PageNav from "../components/shared/partials/PageNav.svelte";
import PageTitle from "../components/shared/ui/PageTitle.svelte";
import { pages } from "../PagesComponentsList.svelte";

export let filterID;
export let title;

const filter = pages.find(i => i.id == filterID);
</script>

<PageTitle title="{title}" />

<PageNav items="{filter.components}" />

{#each filter.components as { id, name, component }, i}
  <div id="{id}">
    <h2 class="text-2xl font-extrabold text-gray-900 mb-4">{name}</h2>
    <!-- <svelte:component this="{component}" filterID="{id}" title="{name}" /> -->
  </div>
{/each}
