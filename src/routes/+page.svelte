<script lang="ts">
  /** @type {import('./$types').LayoutData} */
	export let data:any;
  import Dashboard from "$lib/organisms/dashboard.svelte";
</script>
<div class="p-2 dashboard-container  app-background h-100 w-100">
  <Dashboard data={data.products}></Dashboard>
</div>