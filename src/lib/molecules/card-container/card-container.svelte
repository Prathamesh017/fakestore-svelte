<script lang="ts">
 import {SelectOption,type product } from "../../../common/type";
 import { goto } from '$app/navigation';
 import Card from "../../atoms/card/card.svelte";
 export let data:product[];
 export let selected:SelectOption;
 export let selectedCategories:string[]=[];
 export let searchText:string="";
 export let rating:number;
 export let price:number;
 let filteredData:product[]=data;
 $:if(selected!==SelectOption.Default || searchText || selectedCategories.length>0 || rating || price){
    filteredData=data.sort((item1:product,item2:product)=>{
     return selected===SelectOption.Price?item1.price-item2.price:item2.rating.rate-item1.rating.rate;
    })
    filteredData=filteredData.filter((data)=>{
    return data.title.toLowerCase().startsWith(searchText.toLowerCase());
   })
   if(selectedCategories.length>0){
     filteredData=filteredData.filter((data)=>{
       return selectedCategories.includes(data.category);
      })
    }
    if(rating){
      filteredData=filteredData.filter((data)=>{
        return +data.rating.rate<=rating;
      })
    }
    if(price){
      filteredData=filteredData.filter((data)=>{
        return +data.price<=price;
      })
    }
  }else{
      filteredData=data.sort((item1:product,item2:product)=>{
     return (+item1.id) - (+item2.id)
    })
}

function onCardClick(id:string){
  goto(`/product/${id}`)
}
</script>


<div data-testid="card-container-element"  class="card-container w-full  grid grid-cols-1  lg:grid-cols-3 justify-space-between gap-6">
    {#each  filteredData as item}
        <Card onClick={onCardClick} id={item.id}  label={item.title} price={item.price} rating={item.rating.rate} imageUrl={item.image}></Card>
    {/each}
</div>