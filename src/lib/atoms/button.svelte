<script lang="ts">
  export let onClick:()=>void;
  export let label:string;
  export let classes:string;
</script>


<button on:click={onClick} class={classes}>{label}</button>




