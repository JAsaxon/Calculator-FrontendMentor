<script lang="ts">
    export let number: any;
    export let func: Function;
</script>
<button on:click={func()}>
    {number}
</button>