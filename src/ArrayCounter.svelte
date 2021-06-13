<script lang="ts">
  let array = [0];
  const incrementArray = () => {
    const nextNumber = array.length > 0 ? array[array.length - 1] + 1 : 0;
		array = [...array, nextNumber];
	}

	const decrementArray = () => {
		array = array.slice(1);
	}

  $: sum = array.length > 0 ? array.reduce((left, right) => {
		return left + right;
	}) : 0;
</script>

<p>Array Sum: {sum}</p>
<p>Values in Array:</p>
<button on:click={incrementArray}>Increment Array</button>
<button on:click={decrementArray}>Decrement Array</button>
<div>
  <ul>
    {#each array as value (value + Math.random())}
      <li>{value}</li>
    {/each}
  </ul>
</div>

<style>
  li {
    list-style: none;
    background-color: black;
    border: 1px solid white;
    color: white;
    font-weight: bold;
    width: 50px;
    border-radius: 10px;
    margin: auto;
  }

  ul {
    list-style: none;
    padding-left: 0;
  }

  div {
    background-color: rgb(13, 15, 54);
    width: 200px;
    margin: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 10px;
  }
</style>