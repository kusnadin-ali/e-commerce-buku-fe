<script setup lang="ts">

</script>

<template>
  <UHeader>
    <template #left>
      <div class="flex items-center gap-2">
        <UIcon
          name="i-lucide-library-big"
          class="size-5"
        />
        <h3 class="font-semibold text-lg">
          Books
        </h3>
      </div>
    </template>
    <template #default>
      <UInput
        icon="i-lucide-search"
        placeholder="Cari buku..."
        class="w-64 md:w-80"
      />
    </template>
    <template #right>
      <UButton variant="outlined">
        Login
      </UButton>

      <UButton>
        Register
      </UButton>
    </template>
  </UHeader>
</template>

<style scoped>

</style>
