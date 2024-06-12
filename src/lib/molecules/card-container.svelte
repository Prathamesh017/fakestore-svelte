<script lang="ts">
	import type { product } from "../../common/type";
 import Card from "../atoms/card.svelte";
 export let data:product[];
</script>


<div class="card-container w-full lg:w-4/5  grid grid-cols-2  lg:grid-cols-3 gap-4">
    {#each  data as item}
        <Card label={item.title} price={item.price} rating={item.rating.rate} imageUrl={item.image}></Card>
    {/each}
</div>