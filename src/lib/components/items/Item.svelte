<script lang="ts">
  import { Apple, Pentagon, Triangle } from "@lucide/svelte";

  type Props = {
    locations: {
      name: string;
      textX: number;
      textY: number;
      x: number;
      y: number;
      color: string;
      shape: "square" | "circle" | "triangle" | "pentagon";
    }[];
  };

  let { locations = [] }: Props = $props();
</script>

{#if locations.length > 0}
  {#each locations as location}
    {#if location.shape === "square"}
      <rect
        x={location.x - 10}
        y={location.y - 10}
        width="20"
        height="20"
        fill={location.color}
      />
    {:else if location.shape === "circle"}
      <circle cx={location.x} cy={location.y} r="11" fill={location.color} />
    {:else if location.shape === "triangle"}
      <Triangle
        x={location.x - 19}
        y={location.y - 20}
        size={25}
        color={location.color}
        fill={location.color}
      />
    {:else if location.shape === "pentagon"}
      <Pentagon
        x={location.x - 19}
        y={location.y - 20}
        size={25}
        color={location.color}
        fill={location.color}
      />
    {/if}

    <text x={location.textX} y={location.textY}>{location.name} </text>
    <g transform="translate(-30,-10)">
      {#if location.shape === "square"}
        <rect
          x={location.textX - 10}
          y={location.textY - 10}
          width="20"
          height="20"
          fill={location.color}
        />
      {:else if location.shape === "circle"}
        <circle
          cx={location.textX}
          cy={location.textY}
          r="11"
          fill={location.color}
        />
      {:else if location.shape === "triangle"}
        <Triangle
          x={location.textX - 13}
          y={location.textY - 15}
          size={25}
          color={location.color}
          fill={location.color}
        />
      {:else if location.shape === "pentagon"}
        <Pentagon
          x={location.textX - 13}
          y={location.textY - 15}
          size={25}
          color={location.color}
          fill={location.color}
        />
      {/if}
    </g>
  {/each}
  <!-- each locations -->
{/if}

<!-- if locations -->

<style>
  text {
    fill: black;
    font-size: 32px;
    font-weight: 500;
  }
</style>
