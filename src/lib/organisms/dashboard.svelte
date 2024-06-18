<script lang="ts">
  import CardContainer from "$lib/molecules/card-container/card-container.svelte";
  import { SelectOption, type product } from "../../common/type";
  import Dropdown from "$lib/atoms/dropdown/dropdown.svelte";
	import Category from "$lib/atoms/category/category.svelte";
  import RangeContainer from "$lib/molecules/range-container/range-container.svelte";
  export let data:product[];
  export let selectedCategories:string[]=[];
  export let selected:SelectOption;
  export let onChange:(selected:SelectOption)=>void;
  export let options:string[];
  export let price:number;
  export let rating:number;
  export let searchText:string=""; 
</script>

<div class="dashboard w-full flex mt-2 p-4">
  <div class="category-container-left w-1/5">
    <Category title="Sort With Categories" data={data}></Category>
    <RangeContainer></RangeContainer>
  </div>
  <div class="category-container-right grow">
     <div class="flex justify-end mr-4">
      <Dropdown onChange={onChange} selected={selected}  options={options}></Dropdown>
      </div>
      <div class="flex justify-center">
        <CardContainer rating={rating} price={price}  selectedCategories={ selectedCategories} data={data} selected={selected} searchText={searchText}></CardContainer>
   </div> 
  </div>
</div>