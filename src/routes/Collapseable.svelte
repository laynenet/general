
<script>
    export let title = "";
    export let open = true;
</script>

<div>
    <div class="flex flex-row items-center border-b-1 border-black">
        <div class="w-max-80% h-max-6 overflow-hidden">{title}</div>
        <div class="pl-2">
            {#if open}
                <svg width="1em" height="1em" viewBox="0 0 24 24"><path fill="#888888" d="m7 10l5 5l5-5z"></path></svg>
            {:else}
                <svg width="1em" height="1em" viewBox="0 0 24 24"><path fill="#888888" d="m10 17l5-5l-5-5v10z"></path></svg>
            {/if}
        </div>
    </div>
    <div class="flex flex-col gap-1 border-l-1 border-black ml-1 pl-1">
        <slot></slot>
    </div>
</div>
