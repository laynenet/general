<script>
    export let title = "";
</script>

<style>
    .fullTitle {
        font-size: 30px;
    }
</style>

<div class="w-full h-full overflow-y-auto overflow-x-hidden flex flex-col gap-1 justify-center">
    <div class="flex w-full justify-center my-3">
        <div class="fullTitle w-max border-b-2 border-gray-400 text-gray-300">
            {title}
        </div>
    </div>
    <slot></slot>
</div>
