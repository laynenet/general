
<script>
    export let title = "";
    export let open = true;
    let contentHidden = (open?"":"hid");

    function switchState(){
        open=!open;
        contentHidden = (open?"":"hid");
    }
</script>

<style windi:preflights:global windi:safelist:global>
    .hid {
        display: none;
    }
</style>

<div>
    <div class="flex flex-row items-center border-b-1 border-black">
        <!-- Title -->
        <div class="w-max-80% h-max-6 overflow-hidden text-gray-400">{title}</div>
        <!-- Toggle -->
        <div class="pl-2" on:click={switchState}>
            {#if open}
                <svg class="h-5" viewBox="0 0 24 24"><path fill="#888888" d="m7 10l5 5l5-5z"></path></svg>
            {:else}
                <svg class="h-5" viewBox="0 0 24 24"><path fill="#888888" d="m10 17l5-5l-5-5v10z"></path></svg>
            {/if}
        </div>
    </div>
    <!-- Content -->
    <div class="overflow-hidden {contentHidden}">
        <div class="flex flex-col gap-1 border-l-1 border-black ml-1 pl-1">
            <slot></slot>
        </div>
    </div>
    {#if !open}
        <div class="border-l-1 border-black ml-1 pl-1" on:click={switchState}>
            <svg class="h-4" viewBox="0 0 32 32"><circle cx="16" cy="16" r="8" fill="#888888"></circle></svg>
        </div>
    {/if}
    <div class="ml-1 border-b-1 border-black"></div>
</div>
