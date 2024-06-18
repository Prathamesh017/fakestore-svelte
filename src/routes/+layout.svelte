<script>
  import Header from "$lib/organisms/header.svelte";
import "../app.css";
  import { setContext } from 'svelte';
	import { writable } from 'svelte/store';
	/** @type {import('./$types').LayoutData} */
	// Create a store and update it when necessary...
	const cart = writable([]);
	const searchText=writable("");
	const selectedCategories=writable([]);
	
	setContext('cart', cart);
	setContext("search",searchText);
	setContext("category",selectedCategories);

</script>



<div class="layout"> 
  <Header></Header>
</div>

<slot></slot> 