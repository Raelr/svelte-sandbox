<script lang="ts">
  let counter = 0;
</script>

<p>Your Rating: <b>{counter}/10</b></p>
<input bind:value={counter} type='range' min=0 max=10/>

<style>
  input[type="range"]
  {
      margin: 0px;
      padding: 8px 0px;
      outline: none;
      background-color: transparent;
      -webkit-appearance: none;
  }

  input[type="range"]:focus
  {
      outline: none;
  }

  input[type="range"]::-webkit-slider-runnable-track
  {
      width: 100%;
      height: 4px;
      background: #CCC;
      border-radius: 7px;
      cursor: pointer;
  }

  input[type="range"]:focus::-webkit-slider-runnable-track
  {
      background:#00AD7A;
  }

  input[type="range"]::-webkit-slider-thumb
  {
      height: 18px;
      width: 18px;
      margin-top: -7px;
      border:1px solid #00AD7A;
      background: #00AD7A;
      border-radius: 50%;
      cursor: pointer;
      -webkit-appearance: none;
  }

  input[type="range"]::-moz-range-thumb
  {
      height: 18px;
      width: 18px;
      border:1px solid #00AD7A;
      background: #00AD7A;
      border-radius: 50%;
      cursor: pointer;
  }

  input[type="range"]::-moz-range-track
  {
      width: 100%;
      height: 4px;
      background: #CCC;
      border-radius: 7px;
      cursor: pointer;
  }

  input[type="range"]:focus::-moz-range-track
  {
      background:#00AD7A;
  }

  input[type="range"]::-ms-thumb
  {
      height: 18px;
      width: 18px;
      border:1px solid #00AD7A;
      background: #00AD7A;
      border-radius: 50%;
      cursor: pointer;
  }

  input[type="range"]::-ms-track
  {
      width: 100%;
      height: 4px;
      color: transparent;
      border-width: 16px 0;
      border-color: transparent;
      background: transparent;
      cursor: pointer;
  }

  input[type="range"]::-ms-fill-lower
  {
      background: #CCC;
      border-radius: 3px;
  }

  input[type="range"]::-ms-fill-upper
  {
      background: #CCC;
      border-radius: 3px;
  }

  input[type="range"]:focus::-ms-fill-lower
  {
      background: #00AD7A;
  }

  input[type="range"]:focus::-ms-fill-upper
  {
      background: #00AD7A;
  }
</style>