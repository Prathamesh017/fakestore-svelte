<script lang="ts">
  /** @type {import('./$types').LayoutData} */
	export let data:any;
  import Dashboard from "$lib/organisms/dashboard.svelte";
  import {SelectOption} from "../common/type";
  let selected:SelectOption = SelectOption.Default;
	const options =[
		SelectOption.Default,
		SelectOption.Price,
		SelectOption.Rating
	]
  function onChange(newlySelected:SelectOption){
    selected=newlySelected;
  }


</script>
<div class="p-2 dashboard-container  app-background h-100 w-100">
  <Dashboard bind:selected={selected} onChange={onChange}  options={options} data={data.products}></Dashboard>
</div>