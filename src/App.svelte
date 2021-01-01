<script>
import { Router, Route } from "svelte-routing";
import Header from "./components/shared/partials/Header.svelte";

import PageHome from "./pages/Home.svelte";
import PageFinance from "./pages/Finance.svelte";
import Sidebar from "./components/shared/partials/Sidebar.svelte";

export let url = "";

function handleClick() {
  console.log("no more alerts");
}
</script>

<Header />

<Router url="{url}">
  <div class="md:flex md:items-start container mx-auto mt-8 flex-1">
    <Sidebar />

    <div
      class="w-full md:w-3/4 bg-white border-gray-300 border-solid border p-4 md:ml-8"
    >
      <Route path="finance" component="{PageFinance}" />
      <Route path="/">
        <PageHome />
      </Route>
    </div>
  </div>
</Router>
