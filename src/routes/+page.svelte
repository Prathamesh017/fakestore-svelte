<script lang="ts">
  /** @type {import('./$types').LayoutData} */
	export let data:any;
  import Dashboard from "$lib/organisms/dashboard.svelte";
  import {SelectOption} from "../common/type";
  let selected:SelectOption = SelectOption.Default;
  let searchText:string="";
	const options =[
		SelectOption.Default,
		SelectOption.Price,
		SelectOption.Rating
	]
  function onChange(newlySelected:SelectOption){
    selected=newlySelected;
  }

  function onSearch(search:string){
    searchText=search;
  }


</script>
<div class="p-2 dashboard-container  app-background h-100 w-100">
  <Dashboard bind:selected={selected} onSearch={onSearch} onChange={onChange}  options={options} data={data.products} searchText={searchText}></Dashboard>
</div>