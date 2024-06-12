<script lang="ts">
  export let imageUrl:string;
  export let label:string;
  export let rating:number;
  export let price:number;
</script>

<div class="card  w-36 h-42 lg:w-72 lg:h-72 rounded overflow-hidden shadow-lg bg-white flex flex-col items-center">
  <div class="w-full h-1/2 mt-2 flex justify-center">
    <img class="h-full" src={imageUrl} alt="Sunset in the mountains">
  </div>
  <div class="px-3 py-2 lg:px-6 lg:py-4">
    <p class="lg:font-bold text-sm lg:mb-2">{label}</p> 
  </div>
  <div class="flex flex-col lg:flex-row  items-center justify-between w-full px-5">
    <span class="inline-block">{price} {`\u20B9`}</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">Rating {rating}</span>
  </div>
</div>