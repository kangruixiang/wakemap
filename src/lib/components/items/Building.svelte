<script lang="ts">
  import { ChevronsUpDown } from "@lucide/svelte";

  type Props = {
    x: number;
    y: number;
    width: number;
    height: number;
    title: string;
    title2?: string;
    elevator?: boolean;
  };

  let {
    x,
    y,
    width,
    height,
    title,
    title2,
    elevator = false,
  }: Props = $props();
</script>

<rect {x} {y} class="base" {width} {height} />
<!-- style="fill: {commonBox ? '#3a8390' : 'black'}" -->
<text x={elevator ? x + 75 : x + 50} y={y + 68}>{title}</text>
{#if title2}
  <text x={elevator ? x + 75 : x + 50} y={y + 120}>{title2}</text>
{/if}

{#if elevator}
  <ChevronsUpDown
    x={x + 20}
    y={title2 ? y + 50 : y + 30}
    size={50}
    color="white"
  />
{/if}

<style>
  .base {
    fill: #3a8390;
    rx: 9px;
  }

  text {
    fill: white;
    font-size: 35px;
    font-weight: 400;
  }
</style>
