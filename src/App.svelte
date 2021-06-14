<script lang="ts">
  import NameGetter from './components/NameGetter.svelte';
  import MousePositionGetter from './components/MousePositionGetter.svelte'
  import ArrayCounter from './components/ArrayCounter.svelte';
  import Counter from './components/Counter.svelte';
  import RangeCounter from './components/RangeCounter.svelte';
  import RadioInputTracker from './components/RadioInputTracker.svelte';

	enum DisplayMode {
		COUNT = 0, 
		ARRAY = 1,
		MOUSEMOVE = 2,
		DISPATCH = 3,
    RANGE = 4,
    RADIO = 5,
	}

  const modeNames = [
    'Count',
    'Array',
    `Mouse Position`,
    'Dispatch',
    'Range',
    'Radio'
  ];

	const DISPLAY_MODES = 6;
	export let name: string = 'world';

	let currentMode = DisplayMode.COUNT;

	const toggleMode = () => {
		let newMode = currentMode + 1;
		currentMode = newMode % DISPLAY_MODES;
	}

	const alertName = (event: CustomEvent<any>) => {
		alert(event.detail.text ?? 'No Data');
	}
</script>

<main>
	<h1>Hello {name}!</h1>
  <p>Current Mode: <b>{modeNames[currentMode]}</b></p>
	<button on:click={toggleMode}>Toggle Mode</button>
	{#if currentMode === DisplayMode.COUNT}
    <Counter />
	{:else if currentMode === DisplayMode.ARRAY}
    <ArrayCounter />
	{:else if currentMode === DisplayMode.MOUSEMOVE}
    <MousePositionGetter />
	{:else if currentMode === DisplayMode.DISPATCH}
		<NameGetter on:message={alertName}/>
  {:else if currentMode === DisplayMode.RANGE}
    <RangeCounter />
  {:else}
    <RadioInputTracker />
  {/if}

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>