<script lang="ts">
  type Props = {
    floor: string;
  };
  let { floor }: Props = $props();
</script>

<text x="56" y="110">Floor {floor}</text>

<style>
  text {
    fill: black;
    font-size: 50px;
    font-weight: 500;
  }
</style>
