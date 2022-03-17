
<script>
    import { onMount } from 'svelte';
    import ErrorBG from "./C/ErrorBG.svelte";

    function goHome(){
        location.href = "/";
    }

    $: errArr = [];
    

    function update(){
        errArr = [...errArr, [Math.round(Math.random()*screen.width),Math.round(Math.random()*screen.height)]];
    }

    onMount(() => {
        for(let i=0;i<200;i++){
            update();
        }
    });
</script>

<style windi:preflights:global windi:safelist:global>


</style>


<div class="w-full h-full" on:click={update}>
    
    <!-- Error Display -->
    <div class="flex justify-center items-center w-full h-full">
        <div class="flex flex-col gap-1 w-64 h-35 bg-dark-800 p-2 rounded-md text-light-900">
            <div class="flex flex-row gap-3 w-full text-lg h-8 items-center">
                <svg class="h-full" viewBox="0 0 24 24"><path d="M12.884 2.532c-.346-.654-1.422-.654-1.768 0l-9 17A.999.999 0 0 0 3 21h18a.998.998 0 0 0 .883-1.467L12.884 2.532zM13 18h-2v-2h2v2zm-2-4V9h2l.001 5H11z" fill="#888888"></path></svg>
                <div class="text-blue-400">Uh Oh</div>
                <div class="text-yellow-200">(404)</div>
            </div>
            <div class="text-center">The page you tried to visit does not exist</div>
            <div class="group flex justify-center items-center w-full h-full bg-dark-700 cursor-pointer hover:(bg-dark-500)" on:click={goHome}>
                <div class="group-hover:(text-light-50)">Home</div>
            </div>
        </div>
    </div>

    <!-- Errors BG -->
    <div class="absolute top-0 w-full h-full overflow-hidden pointer-events-none">
        {#each errArr as e}
            <ErrorBG x={e[0]} y={e[1]} />
        {/each}
    </div>
</div>


