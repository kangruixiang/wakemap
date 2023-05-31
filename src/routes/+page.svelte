<script>
  const floors = [
    "Floor SB.png",
    "Floor M.png",
    "Floor G.png",
    "Floor 1.png",
    "Floor 2.png",
    "Floor 3.png",
    "Floor 4.png",
    "Floor 5.png",
    "Floor 6.png",
    "Floor 7.png",
    "Floor 8.png",
    "Floor 9.png",
    "Floor 10.png",
    "Floor 11.png",
  ];
  let floor = 0;
  $: floor > 13 ? (floor = 13) : (floor = floor);
  $: floor < 0 ? (floor = 0) : (floor = floor);
</script>

<main class="px-4 py-4">
  <div class="">
    <img src={floors[floor]} alt="map" class="border-none w-full" />
  </div>
  <div class="mt-4 flex space-x-4 items-center justify-center">
    <button class="btn" on:click={() => (floor = floor -= 1)}>Go Down</button>

    <button class="btn" on:click={() => (floor = floor += 1)}>Go Up</button>
  </div>
</main>
