<script setup lang="ts">


import SideFilter from "~/components/SideFilter.vue";
import CatalogView from "~/components/CatalogView.vue";
</script>

<template class="">
  <div class="grid grid-cols-5 grid-rows-5 gap-4 items-start">
    <div class="col-span-1 row-span-5 col-start-1 row-start-1">
      <SideFilter />
    </div>
    <div class="col-span-4 row-span-5 col-start-2 row-start-1 ">
      <CatalogView/>
    </div>
  </div>
</template>
