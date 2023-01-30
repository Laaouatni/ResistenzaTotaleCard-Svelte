<script>
  export let obj;
  import jsonToMathString from "resistenzatotale-svelteview/scripts/jsonToMathString";
  import { slide } from "svelte/transition";

  let result = eval(`${jsonToMathString(obj)}`);
  let hovered = false;

  $: resultToShow = hovered
    ? `${result}`
    : !`${result}`.includes(".")
    ? `${result}`
    : `${result}`.split(".")[0] +
      "." +
      (`${result}`.split(".")[1].length > 2
        ? `${result}`.split(".")[1].substring(0, 2) + "..."
        : `${result}`.split(".")[1]);
</script>

<div
  on:mouseenter={() => (hovered = true)}
  on:mouseleave={() => (hovered = false)}
>
  {#key resultToShow}
    <div transition:slide>{resultToShow}Ω</div>
  {/key}
</div>
