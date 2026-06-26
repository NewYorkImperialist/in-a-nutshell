<script lang="ts">
  import Word from "$lib/components/Word.svelte";
  
  type Role = "prompter" | "guesser";

  interface Props {
    words: string[];
    answer: string;
    role: Role;
  };

  const { words, answer, role }: Props = $props();
</script>

<div class="flex flex-col gap-6">
  <ul class="flex flex-col gap-2 items-stretch">
    {#each words as word}
      <Word {word} toggleable={role === "prompter"} />
    {/each}
  </ul>

  {#if role === "prompter"}
    <Word word={answer} toggleable={false} />
  {:else}
    <!-- TODO: eliminate this input's min-width PLEASE -->
    <input 
      class="min-w-0 px-3 py-1 bg-zinc-800 rounded uppercase text-center text-xl font-bold tracking-tight"
    />
  {/if}

  <button 
    class="px-3 py-1 bg-blue-800 hover:bg-blue-700 transition-colors rounded uppercase text-center text-xl font-bold tracking-tight"
  >
    submit
  </button>
</div>
