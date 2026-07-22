<script setup>

import Navbar from "~/components/Navbar.vue";
</script>

<template>
  <UApp>
    <Navbar/>

    <UMain class="py-4 px-5 h-full ">
      <NuxtPage/>
    </UMain>


  </UApp>
</template>
