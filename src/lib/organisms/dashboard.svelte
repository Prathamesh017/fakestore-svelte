<script lang="ts">
  import CardContainer from "../molecules/card-container.svelte";
  import type { product } from "../../common/type";
  export let data:product[];
</script>

<div class="dashboard flex w-full justify-center">
  <CardContainer data={data}></CardContainer>
</div>