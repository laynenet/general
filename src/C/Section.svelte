<script>
    export let title = "";
    export let stateChangeable = true;
    export let state = true;

    function swapState(){
        state=!state;
    }
</script>

<style>
    .secTitle {
        font-size: 25px;
    }
</style>

<div class="mx-8 my-2 overflow-y-auto overflow-x-hidden border-black border-2 rounded-xl px-2 py-1 bg-dark-300">
    <div class={state? "border-gray-400 border-b-1 mb-2" : ""}>
        <div class="flex flex-row items-center">
            <div class="secTitle mr-3 text-cool-gray-500 align-middle">
                {title}
            </div>
            {#if stateChangeable}
            <div class="transition-colors duration-300 h-full rounded-full hover:(bg-dark-100) active:(bg-dark-50)" on:click={swapState}>
                <svg class="h-8 fill-cool-gray-500" viewBox="0 0 24 24">
                    {#if state}
                        <path d="M8.12 9.29L12 13.17l3.88-3.88a.996.996 0 1 1 1.41 1.41l-4.59 4.59a.996.996 0 0 1-1.41 0L6.7 10.7a.996.996 0 0 1 0-1.41c.39-.38 1.03-.39 1.42 0z"></path>
                    {:else}
                        <path d="M9.29 15.88L13.17 12L9.29 8.12a.996.996 0 1 1 1.41-1.41l4.59 4.59c.39.39.39 1.02 0 1.41L10.7 17.3a.996.996 0 0 1-1.41 0c-.38-.39-.39-1.03 0-1.42z"></path>
                    {/if}
                </svg>
            </div>
            {/if}
        </div>
    </div>
    <div class={state ? "pb-1" : "hidden"}>
        <slot></slot>
    </div>

</div>
