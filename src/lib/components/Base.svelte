<script lang="ts">
  import type { Snippet } from "svelte";
  import { ChevronsUpDown } from "@lucide/svelte";

  import Building from "$lib/components/items/Building.svelte";
  import Floor from "$lib/components/items/Floor.svelte";

  type Props = {
    floor: string;
    hall: Snippet;
    location: Snippet;
  };

  let { floor, hall, location }: Props = $props();

  let mouse = $state({ x: 0, y: 0 });
  let svgEl;

  function handleMouseMove(event) {
    const rect = svgEl.getBoundingClientRect();
    const x = event.clientX - rect.left;
    const y = event.clientY - rect.top;

    const viewBox = svgEl.viewBox.baseVal;
    const scaleX = viewBox.width / rect.width;
    const scaleY = viewBox.height / rect.height;

    mouse = {
      x: +(x * scaleX).toFixed(0),
      y: +(y * scaleY).toFixed(0),
    };
  }
</script>

<div class="border-base-300 rounded-md border-2">
  <!-- svelte-ignore a11y_no_static_element_interactions -->
  <svg
    bind:this={svgEl}
    onmousemove={handleMouseMove}
    viewBox="0 0 2010 1034"
    fill="none"
  >
    <rect width="2010" height="1034" rx="8" fill="#F7F9F9" />

    <Floor {floor} />

    {@render hall()}

    <Building
      x={53}
      y={335}
      width={270}
      height={108}
      title="Common"
      elevator={true}
    />

    <Building x={272} y={190} width={210} height={108} title="Parking" />

    <Building
      x={486}
      y={335}
      width={300}
      height={108}
      title="Watlington"
      elevator={true}
    />

    <Building
      x={862}
      y={311}
      width={250}
      height={156}
      title="Reynold"
      title2="Tower"
      elevator={true}
    />

    <Building
      x={1327}
      y={115}
      width={210}
      height={158}
      title="Sticht"
      title2="Center"
      elevator={true}
    />

    <Building
      x={1227}
      y={335}
      width={350}
      height={108}
      title="Janeway Tower"
      elevator={true}
    />

    <Building
      x={1720}
      y={340}
      width={180}
      height={160}
      title="New"
      title2="Tower"
    />

    <Building
      x={865}
      y={556}
      width={300}
      height={108}
      title="North Tower"
      elevator={true}
    />

    <Building x={1227} y={556} width={340} height={108} title="Ardmore Tower" />

    <Building
      x={1760}
      y={526}
      width={220}
      height={160}
      title="Brenner"
      title2="Tower"
    />

    {#if floor === "G"}
      <Building
        x={1482}
        y={795}
        width={320}
        height={156}
        title="Cancer Center"
        title2="Floor 4"
        elevator={true}
      />
    {:else if floor === "2"}
      <Building
        x={1482}
        y={795}
        width={320}
        height={156}
        title="Cancer Center"
        title2="Floor 6"
        elevator={true}
      />
    {:else if floor === "4"}
      <Building
        x={1482}
        y={795}
        width={320}
        height={156}
        title="Cancer Center"
        title2="Floor 8"
        elevator={true}
      />
    {:else}
      <Building
        x={1550}
        y={795}
        width={230}
        height={156}
        title="Cancer"
        title2="Center"
        elevator={true}
      />
    {/if}

    <rect x="1640" y="585" width="60" height="80" rx="5" fill="#3a8390" />
    <ChevronsUpDown x="1645" y="600" size={50} color="white" />

    <ChevronsUpDown x="87" y="928" size={50} color="black" />
    <text x="150" y="970" font-size="40px">Elevator</text>

    {@render location()}
  </svg>
</div>

<!-- {mouse.x}
{mouse.y} -->

<style>
  text {
    fill: black;
    font-size: 46px;
    font-weight: 500;
  }
</style>
