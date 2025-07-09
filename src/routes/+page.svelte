<script lang="ts">
  import Base from "$lib/components/Base.svelte";
  import {
    M,
    G,
    Floor1,
    Floor2,
    Floor3,
    Floor4,
    Floor5,
    Floor6,
    Floor7,
    Floor8,
    Floor9,
    Floor10,
    Floor11,
    Floor12,
    SB,
  } from "$lib/components/floor/index";
  import Item from "$lib/components/items/Item.svelte";

  let floor = $state(1);

  const rose = "#d39090";

  const floors = [
    {
      name: "SB",
      hall: SB,
      locations: [
        {
          name: "Emergency Department",
          textX: 100,
          textY: 580,
          x: 1740,
          y: 417,
          color: "black",
          shape: "square",
        },
      ],
    },
    {
      name: "M",
      hall: M,
      locations: [
        {
          name: "Horseshoe Entrance",
          textX: 100,
          textY: 580,
          x: 1161,
          y: 437,
          color: "black",
          shape: "triangle",
        },
        {
          name: "Pharmacy and Gift Shop",
          textX: 100,
          textY: 630,
          x: 1400,
          y: 530,
          color: "black",
          shape: "circle",
        },
        {
          name: "Cafeteria",
          textX: 100,
          textY: 730,
          x: 1890,
          y: 550,
          color: rose,
          shape: "circle",
        },
        {
          name: "Starbucks",
          textX: 100,
          textY: 680,
          x: 1313,
          y: 472,
          color: rose,
          shape: "triangle",
        },
      ],
    },
    {
      name: "G",
      hall: G,
      locations: [
        {
          name: "CDU",
          textX: 100,
          textY: 580,
          x: 1780,
          y: 610,
          color: "black",
          shape: "square",
        },
        {
          name: "Camino Coffee",
          textX: 100,
          textY: 630,
          x: 920,
          y: 342,
          color: rose,
          shape: "triangle",
        },
        {
          name: "Chick-fil-A",
          textX: 100,
          textY: 680,
          x: 913,
          y: 446,
          color: rose,
          shape: "circle",
        },
        {
          name: "Subway",
          textX: 100,
          textY: 730,
          x: 878,
          y: 414,
          color: rose,
          shape: "square",
        },
        {
          name: "Endoscopy and Bronchoscopy",
          textX: 100,
          textY: 780,
          x: 986,
          y: 334,
          color: "black",
          shape: "circle",
        },
      ],
    },
    {
      name: "1",
      hall: Floor1,
      locations: [
        {
          name: "Cardiology Offices",
          textX: 100,
          textY: 580,
          x: 562,
          y: 350,
          color: "black",
          shape: "square",
        },
        {
          name: "Hematology Oncology Offices",
          textX: 100,
          textY: 630,
          x: 600,
          y: 350,
          color: "black",
          shape: "circle",
        },
      ],
    },
    {
      name: "2",
      hall: Floor2,
      locations: [
        {
          name: "ACE Unit",
          textX: 100,
          textY: 580,
          x: 1370,
          y: 240,
          color: "black",
          shape: "triangle",
        },
        {
          name: "Hemeonc and Leukemia Workrooms",
          textX: 100,
          textY: 630,
          x: 1580,
          y: 817,
          color: "black",
          shape: "circle",
        },
        {
          name: "Pulmonary Critical Care Offices",
          textX: 100,
          textY: 680,
          x: 751,
          y: 355,
          color: "black",
          shape: "square",
        },
      ],
    },
    {
      name: "3",
      hall: Floor3,
      locations: [
        {
          name: "Conference Room 8",
          textX: 100,
          textY: 580,
          x: 630,
          y: 355,
          color: "black",
          shape: "square",
        },
        {
          name: "Internal Medicine Offices",
          textX: 100,
          textY: 630,
          x: 715,
          y: 355,
          color: "black",
          shape: "circle",
        },
      ],
    },
    {
      name: "4",
      hall: Floor4,
      locations: [
        {
          name: "MICU A, B, C",
          textX: 100,
          textY: 580,
          x: 900,
          y: 340,
          color: "black",
          shape: "square",
        },
        {
          name: "MICU O",
          textX: 100,
          textY: 730,
          x: 1530,
          y: 820,
          color: "black",
          shape: "circle",
        },
        {
          name: "MICU A, B, C",
          textX: 100,
          textY: 630,
          x: 1084,
          y: 641,
          color: "black",
          shape: "square",
        },

        {
          name: "Dialysis Center",
          textX: 100,
          textY: 680,
          x: 1043,
          y: 580,
          color: "black",
          shape: "triangle",
        },
        {
          name: "Cath Lab",
          textX: 100,
          textY: 780,
          x: 1789,
          y: 612,
          color: "black",
          shape: "pentagon",
        },
      ],
    },
    {
      name: "5",
      hall: Floor5,
      locations: [
        {
          name: "Stroke and Neurology Floor",
          textX: 100,
          textY: 580,
          x: 1537,
          y: 632,
          color: "black",
          shape: "triangle",
        },
        {
          name: "Neuro ICU",
          textX: 100,
          textY: 630,
          x: 1784,
          y: 617,
          color: "black",
          shape: "circle",
        },
      ],
    },
    {
      name: "6",
      hall: Floor6,
      locations: [
        {
          name: "IMC",
          textX: 100,
          textY: 580,
          x: 911,
          y: 340,
          color: "black",
          shape: "square",
        },
      ],
    },
    {
      name: "7",
      hall: Floor7,
      locations: [
        {
          name: "CVICU and CTICU",
          textX: 100,
          textY: 580,
          x: 1036,
          y: 574,
          color: "black",
          shape: "square",
        },
        {
          name: "CF Clinic",
          textX: 100,
          textY: 730,
          x: 1787,
          y: 573,
          color: "black",
          shape: "circle",
        },
        {
          name: "Cardiology Reynolds",
          textX: 100,
          textY: 630,
          x: 913,
          y: 346,
          color: "black",
          shape: "triangle",
        },
        {
          name: "Cardiology Ardmore",
          textX: 100,
          textY: 680,
          x: 1381,
          y: 650,
          color: "black",
          shape: "pentagon",
        },
      ],
    },
    {
      name: "8",
      hall: Floor8,
      locations: [
        {
          name: "Nephrology Workroom",
          textX: 100,
          textY: 580,
          x: 1021,
          y: 575,
          color: "black",
          shape: "square",
        },
        {
          name: "Winston 1 Workroom",
          textX: 100,
          textY: 630,
          x: 1354,
          y: 575,
          color: "black",
          shape: "circle",
        },
      ],
    },
    {
      name: "9",
      hall: Floor9,
      locations: [
        {
          name: "Winston 2 Workroom",
          textX: 100,
          textY: 580,
          x: 1078,
          y: 575,
          color: "black",
          shape: "square",
        },
      ],
    },
    {
      name: "10",
      hall: Floor10,
      locations: [],
    },
    {
      name: "11",
      hall: Floor11,
      locations: [],
    },
    {
      name: "12",
      hall: Floor12,
      locations: [
        {
          name: "Rooftop Courtyard",
          textX: 100,
          textY: 580,
          x: 1786,
          y: 605,
          color: rose,
          shape: "circle",
        },
      ],
    },
  ];
</script>

<div class="grid grid-cols-12 p-2 gap-x-2">
  <div class="md:col-span-11 col-span-12">
    <Base floor={floors[floor]["name"]}>
      {#snippet hall()}
        {@const Hall = floors[floor]["hall"]}
        <Hall />
      {/snippet}
      {#snippet location()}
        <Item locations={floors[floor]["locations"]} />
      {/snippet}
    </Base>
  </div>
  <div
    class="md:col-span-1 col-span-12 min-h-10 gap-2 grid grid-cols-2 md:grid-cols-1"
  >
    <button
      disabled={floor === 0}
      onclick={() => (floor -= 1)}
      class="btn btn-soft w-full h-full md:order-2">Down</button
    >
    <button
      disabled={floor === 14}
      onclick={() => (floor += 1)}
      class="btn btn-soft w-full h-full">Up</button
    >
  </div>
  <div class="text-zinc-400 text-sm text-right mt-8 md:mt-1 mx-3 col-span-12">
    Made by <a href="https://projects.krxiang.com" class="link"
      >Kang Rui Xiang</a
    >.
  </div>
</div>
