<script>
    import { onMount } from 'svelte';
    export let x = 0;
    export let y = 0;

    let errDiv;

    onMount(() => {

        errDiv.style.left=x+"px";
        errDiv.style.top=y+"px";
    });

</script>

<style>
    .err-bg{
        position: absolute;
        width:2.5rem;
    }
</style>

<div bind:this={errDiv} class="err-bg" style="">
    <svg  viewBox="0 0 24 24"><path d="M12.884 2.532c-.346-.654-1.422-.654-1.768 0l-9 17A.999.999 0 0 0 3 21h18a.998.998 0 0 0 .883-1.467L12.884 2.532zM13 18h-2v-2h2v2zm-2-4V9h2l.001 5H11z" fill="#88888822"></path></svg>
</div>