<script>
  import "../app.css";
  import { setContext } from 'svelte';
	import { writable } from 'svelte/store';
	/** @type {import('./$types').LayoutData} */
	// Create a store and update it when necessary...
	const cart = writable([]);
	
	setContext('cart', cart);
</script>



<div class="layout"> 
  <h1 class="p-2 heading-text-color text-3xl">Fake Store</h1>
</div>

<slot></slot> 