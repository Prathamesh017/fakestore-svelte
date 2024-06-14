<script lang="ts">
  import CardContainer from "$lib/molecules/card-container.svelte";
  import { SelectOption, type product } from "../../common/type";
  import Dropdown from "$lib/atoms/dropdown/dropdown.svelte";
	import Input from "$lib/atoms/input.svelte";
  export let data:product[];
  export let selected:SelectOption;
  export let onChange:(selected:SelectOption)=>void;
  export let options:string[];
  export let searchText:string="";
  export let onSearch:(search:string)=>void;
  
  
</script>

<div class="dashboard w-full flex flex-col">
  <div class="flex flex-row justify-between mt-4">
    <div>
      <Input placeholder="search for product" onSearch={onSearch} classes="p-1 text-center rounded"></Input>
    </div>
    <div class="flex justify-end mr-4">
      <Dropdown onChange={onChange} selected={selected}  options={options}></Dropdown>
    </div>
  </div>
   <div class="flex justify-center">
     <CardContainer data={data} selected={selected} searchText={searchText}></CardContainer>
   </div>
</div>