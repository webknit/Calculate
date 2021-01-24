<script>
  import PageTitle from "../components/shared/ui/PageTitle.svelte";
  import { pages } from "../PagesComponentsList.svelte";

  const items = pages.filter(i => i.id !== "home");

  console.log(items);
</script>

<PageTitle title="Home" />

<p>
  A collection of tools for those pesky calculations. Made by
  <a href="www.webknit.console.uk" class="underline">Webknit</a>
  with
  <a href="https://svelte.dev/" class="underline">Sevelte</a>
  and everything else is handled by
  <a href="https://vercel.com/" class="underline">Vecel</a>.
</p>

{#each items as item}
  <div class="mt-8">
    <h2 class="text-2xl font-extrabold text-gray-900 mt-4">{item.name}</h2>
    <ul class="text-purple-800">
      {#each item.components as component}
        <li>
          <a
            href="{item.path}#{component.id}"
            class=" hover:underline"
          >{component.name}</a>
        </li>
      {/each}
    </ul>
  </div>
{/each}
