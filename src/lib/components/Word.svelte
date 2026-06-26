<script lang="ts">
  import { Check, X } from "@lucide/svelte";

  interface Props {
    word: string;
    enabled?: boolean;
    toggleable?: boolean;
  };

  let { word, enabled = true, toggleable = true }: Props = $props();

  const toggle = () => enabled = !enabled;
</script>

<li class="flex items-center gap-2">
  <div class="px-3 py-1 flex-1 bg-zinc-800 rounded uppercase">
    <p 
      class="text-center text-xl font-bold tracking-tight select-none"
      class:invisible={!enabled}
    >
      {word}
    </p>
  </div>
  {#if toggleable}
    <button 
      onclick={toggle}
      class="{enabled 
        ? 'text-green-500 bg-green-500/20 hover:bg-green-500/25' 
        : 'text-red-500 bg-red-500/20 hover:bg-red-500/25'} transition-colors p-1 rounded"
    >
      {#if enabled}
        <Check />
      {:else}
        <X />
      {/if}
    </button>
  {/if}
</li>
