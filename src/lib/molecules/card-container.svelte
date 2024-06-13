<script lang="ts">
 import {SelectOption,type product } from "../../common/type";
 import { goto } from '$app/navigation';
 import Card from "../atoms/card.svelte";
 export let data:product[];
 export let selected:SelectOption;
 let filteredData:product[]=data;
 $:if(selected!==SelectOption.Default){
    filteredData=filteredData.sort((item1:product,item2:product)=>{
     return selected===SelectOption.Price?item1.price-item2.price:item2.rating.rate-item1.rating.rate;
    })

  }else{
      filteredData=filteredData.sort((item1:product,item2:product)=>{
     return (+item1.id) - (+item2.id)
    })
}

function onCardClick(id:string){
  goto(`/product/${id}`)
}
</script>


<div class="card-container w-full lg:w-4/5  grid grid-cols-2  lg:grid-cols-3 gap-4">
    {#each  filteredData as item}
        <Card onClick={onCardClick} id={item.id}  label={item.title} price={item.price} rating={item.rating.rate} imageUrl={item.image}></Card>
    {/each}
</div>