<script>
  export let obj;
  import ResistenzaTotaleSvelteView from "resistenzatotale-svelteview/ResistenzaTotale.svelte";
  import { slide } from "svelte/transition";
  import Dropdown from "./Dropdown.svelte";
  import RtNumber from "./RtNumber.svelte";
</script>

<Dropdown>
  <div slot="info" class="flex content-center text-2xl items-center gap-2">
    <h2 class="font-bold">Rt =</h2>
    <RtNumber {obj} />
  </div>

  <div slot="detail" transition:slide class="grid place-items-center">
    <ResistenzaTotaleSvelteView value={obj} />
  </div>
</Dropdown>
