<script>
  import Button from "./Button.svelte";

  let dropdownOpen = false;
</script>

<div
  class="grid gap-4 p-4 rounded-xl rounded-l-none border-l-8 border-2 border-blue-400 bg-gray-50 shadow-md transition w-full"
>
  <div class="flex justify-between gap-4">
    <slot name="info"><!-- optional fallback --></slot>
    <Button on:click={() => (dropdownOpen = !dropdownOpen)}
      >{dropdownOpen ? "🡱 chiudi" : "🡳 vedi i calcoli"}</Button
    >
  </div>

  {#if dropdownOpen}
    <slot name="detail"><!-- optional fallback --></slot>
  {/if}
</div>
