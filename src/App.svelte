<script>
import { Router, Route } from "svelte-routing";

import Header from "./components/shared/partials/Header.svelte";
import Sidebar from "./components/shared/partials/Sidebar.svelte";

export let url = "";

import { pages } from "./PagesComponentsList.svelte";
</script>

<Header />

<Router url="{url}">
  <div class="md:flex md:items-start container mx-auto mt-8 px-4 flex-1">
    <Sidebar pages="{pages}" />
    <div
      class="w-full md:w-3/4 bg-white border-gray-300 border-solid border p-4 md:ml-8"
    >
      {#each pages as { path, component, name, id }, i}
        {#if id == 'home'}
          <Route path="{path}">
            <svelte:component this="{component}" />
          </Route>
        {:else}
          <Route path="{path}">
            <svelte:component
              this="{component}"
              filterID="{id}"
              title="{name}"
            />
          </Route>
        {/if}
      {/each}
    </div>
  </div>
</Router>
