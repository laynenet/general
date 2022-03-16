<script>
    import Collapsible from "./Collapsible.svelte";

    export let data = {};
    let dataKeys = Object.keys(data);
</script>


{#each Object.values(data) as d,id}
    {#if typeof d == "object"}
        <!-- Collapislbe Object Content -->
        <Collapsible title={dataKeys[id]}>
            <svelte:self data={d}/>
        </Collapsible>
    {:else}
        <!-- Name & Link Content -->
        <div><a href={d}>{dataKeys[id]}</a></div>
    {/if}
{/each}


