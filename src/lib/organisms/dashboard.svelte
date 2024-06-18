<script lang="ts">
  import CardContainer from "$lib/molecules/card-container.svelte";
  import { SelectOption, type product } from "../../common/type";
  import Dropdown from "$lib/atoms/dropdown/dropdown.svelte";
  export let data:product[];
  export let selected:SelectOption;
  export let onChange:(selected:SelectOption)=>void;
  export let options:string[];
  export let searchText:string=""; 
</script>

<div class="dashboard w-full flex flex-col">
    <div class="flex justify-end mr-4">
      <Dropdown onChange={onChange} selected={selected}  options={options}></Dropdown>
    </div>
   <div class="flex justify-center">
     <CardContainer data={data} selected={selected} searchText={searchText}></CardContainer>
   </div>
</div>