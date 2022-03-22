<script>
import { onMount } from "svelte";


    export let obj = [];
    $: state = [];

    function swapState(n){
        return () => {
            state[n]=!state[n];
        }
    }

    onMount(() => {
        for(var i=0;i<obj.length;i++){
            state = [...state, true];
        }
    })
</script>



<div class="flex flex-col">
    {#each obj as o,i}
        {#if o.type == "container"}
            <div class="flex flex-row h-max items-center">
                <div on:click={swapState(i)}>
                    <svg class="h-4 fill-cool-gray-500" viewBox="0 0 24 24">
                        {#if state[i]}
                            <path d="M8.12 9.29L12 13.17l3.88-3.88a.996.996 0 1 1 1.41 1.41l-4.59 4.59a.996.996 0 0 1-1.41 0L6.7 10.7a.996.996 0 0 1 0-1.41c.39-.38 1.03-.39 1.42 0z"></path>
                        {:else}
                            <path d="M9.29 15.88L13.17 12L9.29 8.12a.996.996 0 1 1 1.41-1.41l4.59 4.59c.39.39.39 1.02 0 1.41L10.7 17.3a.996.996 0 0 1-1.41 0c-.38-.39-.39-1.03 0-1.42z"></path>
                        {/if}
                    </svg>
                </div>
                <div>{o.name}</div>
            </div>
            {#if state[i]}
            <div class="pl-1 ml-1.6 border-l-2 border-black">
                <svelte:self obj={o.keys}/>
            </div>
            {/if}
        {:else}
            <div class="flex flex-row h-max items-center">
                <svg class="h-4" viewBox="0 0 24 24"><path fill="#888888" d="M12 16a4 4 0 1 1 0-8a4 4 0 0 1 0 8Z"></path></svg>
                <div>{o.name}</div>
            </div>
        {/if}
    {/each}
</div>
