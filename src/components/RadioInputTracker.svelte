<script lang="ts">

let selectedSize = 'small';

const addons = [
  'logo',
  'name',
  'color',
]

const sizes = [
  'small',
  'medium',
  'large',
]

let selectedAddons: string[] = [];

</script>

<p>Please select what size shirt you'd like.</p>
<p>You selected a <b>{selectedSize}</b> shirt. </p>
{#if selectedAddons.length > 0}
  <p>You also selected the following addons: {selectedAddons.join(', ')}.</p>
{:else}
  <p>You have selected no addons for the shirt.</p>
{/if}
<h2>Size</h2>
{#each sizes as size}
  <label>
    <input type='radio' bind:group={selectedSize} value={size}/>
    {size[0].toUpperCase() + size.slice(1)}
  </label>
{/each}
<h2>Addons</h2>
{#each addons as addon}
  <label>
    <input type='checkbox' bind:group={selectedAddons} value={addon}/>
    {addon}
  </label>
{/each}

<style>

</style>