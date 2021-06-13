<script lang="ts">
  let message = 'Count is a decent size';
	let count = 0;

  const incrementCount = () => {
    count += 1;
	}

  $: doubled = count * 2;

  $: if (count >= 10) {
    message = 'Count is getting pretty high...'
  }
</script>

<div>
  <p><span><b>{count}</b></span></p>
  <p><span>Doubled: <b>{doubled}</b></span></p>
  <p><span class={count >= 10 ? 'highCount' : 'button'}><b>{message}</b></span></p>
  <button on:click={incrementCount}>Click me!</button>
</div>

<style>
  p {
    margin-bottom: 25px;
  }
  span {
    background-color: black;
    color: white;
    padding: 10px;
    border-radius: 10px;
    border: 1px solid white;
    width: 10%;
  }
  .highCount {
    color: white;
    background-color: red;
  }

  button {
    background-color: rgb(31, 30, 30);
    border: 1px solid black;
    color: white;
    border-radius: 10px;
    cursor: pointer;
    border: 1px solid white;
  }

  button:hover {
    background-color: white;
    color: black;
    border: 1px solid white;
    transition: 0.1s;
  }

  div {
    display: flex;
    align-items: center;
    flex-direction: column;
    margin: 10px;
    background-color: rgb(13, 15, 54);
    padding: 5px;
    width: 300px;
    text-align: center;
    margin: auto;
    border-radius: 10px;
  }
</style>