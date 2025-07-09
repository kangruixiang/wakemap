<script lang="ts">
  import Button from "$lib/components/Button.svelte";
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
  let floor = $state(0);
</script>

<main class="px-4 py-4">
  <div class="">
    <img src={floors[floor]} alt="map" class="border-none w-full" />
    <div class="text-zinc-400 text-sm text-right mt-1 mx-3">
      Made by <a href="https://projects.krxiang.com">Kang Rui Xiang</a>.
    </div>
  </div>
  <div class="mt-4 flex space-x-4 items-center justify-center">
    <Button disabled={floor == 0} onclick={() => (floor = floor -= 1)}
      >Go Down</Button
    >

    <Button disabled={floor == 13} onclick={() => (floor = floor += 1)}
      >Go Up</Button
    >
  </div>
</main>
