<script lang="ts">
  import Tower from "$lib/components/Tower.svelte";

  const words = ["which", "swiss", "watch", "brand", "features", "a", "distinctive", "crown"];
</script>

<div class="flex-1 p-12 flex flex-col items-center gap-6">
  <Tower 
    {words} 
    answer="rolex"
    role="guesser"
  />
</div>
