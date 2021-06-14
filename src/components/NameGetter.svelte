<script lang="ts">
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    let name = '';

    const getName = () => {
        dispatch('message', {
            text: `Hello ${name.length > 0 ? name : 'No Name'}!`,
        })
    }
</script>

<p>Type your name in:</p>
<button on:click={getName}>Click to Say Hello!</button>
<input bind:value={name}/>

<style>

</style>