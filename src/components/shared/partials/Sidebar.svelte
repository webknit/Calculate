<script>
import { Link } from "svelte-routing";
</script>

<div class="w-full md:w-1/4 bg-white border-gray-300 border-solid border">
  <nav>
    <Link class="border-gray-300 border-solid border-b block p-4" to="/">
      Home
    </Link>
    <Link class="block p-4" to="finance">Finance</Link>
  </nav>
</div>
