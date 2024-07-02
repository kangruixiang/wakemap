<script lang="ts">
  import { cn } from "$lib/components/utils";
  let {children, ...other} = $props()
</script>

<button class="px-6 py-3 rounded border-2 border-black  active:scale-[0.99] h-14 tracking-wider font-semibold bg-zinc-100 active:shadow-[inset_0px_1px_0px_0px_black]" {...other}>
  {@render children()}
</button>