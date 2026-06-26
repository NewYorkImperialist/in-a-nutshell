<script lang="ts">
  import Tower from "$lib/components/Tower.svelte";
  import { promptData } from './prompts'
  const prompt = promptData[Math.floor(Math.random() * (promptData.length + 1))]
  const words = prompt.description;
</script>

<div class="flex-1 p-12 flex flex-col items-center gap-6">
  <Tower 
    {words} 
    answer={prompt.answer}
    role="guesser"
  />
</div>
