<script>
export let value;
</script>

<div class="text-purple-900 text-3xl font-bold">
  {#if value}
    <p class="">{value}</p>
  {/if}
  <slot />
</div>
