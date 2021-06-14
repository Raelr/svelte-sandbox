<script lang="ts">

let mousePos = {x: 0, y: 0};

const setMousePos = (event: MouseEvent) => {
  mousePos = { x: event.clientX, y: event.clientY };
}
</script>

<p>Mouse position is: {mousePos.x} x {mousePos.y}</p>
<div on:mousemove={setMousePos} />

<style>
	div { 
    width: 100%; 
    height: 500px; 
    border: 1px solid black; 
  }
</style>