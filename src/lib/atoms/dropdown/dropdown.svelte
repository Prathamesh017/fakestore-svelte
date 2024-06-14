 <script lang="ts">
	import type { SelectOption } from "../../../common/type";

  export let selected:string="";
  export let options:string[]=[];
  export let onChange:(selected:SelectOption)=>void;
</script>

<select on:change={(e)=>onChange(e.target?.value)} bind:value={selected} class="bg-primary-700 hover:bg-primary-800  focus:ring-primary-300 font-medium rounded-lg text-sm px-4 py-2.5 text-center">
	{#each options as value}<option {value}>{value} </option>{/each}
</select>