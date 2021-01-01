<script>
import { Link } from "svelte-routing";
export let pages;
</script>

<div class="w-full md:w-1/4 bg-white border-gray-300 border-solid border mb-4">
  <nav>
    {#each pages as { path, name }, i}
      <Link
        class="block p-4 {i < pages.length - 1 ? 'border-gray-300 border-solid border-b' : ''}"
        to="{path}"
      >
        {name}
      </Link>
    {/each}
  </nav>
</div>
