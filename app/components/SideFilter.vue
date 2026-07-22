<script setup lang="ts">
const itemCategories = ref(['Fiksi', 'Non-Fiksi', 'Bisnis', 'Pendidikan', 'Pendidikan', 'Teknologi'])
const selectCategory = ref([''])
const itemWriters = ref(['Budi Santoso', 'Siti Aminah', 'Joko Widodo', 'Devi Lestari'])
const selectWriter = ref('')
const minPrice = ref<number | null>(null)
const maxPrice = ref<number | null>(null)

const itemSorting = ref(['Terbaru', 'Harga Terendah', 'Harga Tertinggi', 'Rekomendasi', 'Terlaris'])
const selectSorting = ref('')
</script>

<template class="h-full">
  <UCard class="h-full">
    <template #header>
      <p class="text-xl font-bold">
        Filter
      </p>
    </template>

    <!-- Filter Kategori   -->
    <div>
      <p class="font-bold mb-1">
        Kategori
      </p>

      <UCheckboxGroup v-model="selectCategory" :items="itemCategories"/>
    </div>

    <br>
    <USeparator/>
    <br>
    <!-- Filter Penulis   -->
    <div>
      <p class="font-bold mb-1">
        Penulis
      </p>

      <USelectMenu
        v-model="selectWriter"
        :items="itemWriters"
        class="w-full"
        clear
        placeholder="Semua Penulis"

      />
    </div>

    <br>
    <USeparator/>
    <br>
    <!-- Filter Harga   -->
    <div>
      <p class="font-bold mb-2">
        Harga
      </p>

      <!--
        grid-cols-1: Default (di HP) menumpuk ke bawah
        sm:grid-cols-5: Di layar medium ke atas (sm) berubah menjadi 5 kolom grid
      -->
      <div class="grid grid-cols-1 sm:grid-cols-11 items-center gap-2 mb-4">

        <!-- Input Min Harga -->
        <div class="w-full sm:col-span-5">
          <UInput
            v-model="minPrice"
            type="number"
            placeholder="Min"
            icon="i-lucide-tag"
            class="w-full"
          >
            <template #leading>
              <span class="text-xs text-gray-500 font-semibold px-1">Rp</span>
            </template>
          </UInput>
        </div>

        <!-- Tanda Hubung (-) -->
        <!-- text-center agar pas di tengah saat menumpuk di HP -->
        <div class="text-center text-gray-400 font-medium sm:col-span-1">
          -
        </div>

        <!-- Input Max Harga -->
        <div class="w-full sm:col-span-5">
          <UInput
            v-model="maxPrice"
            type="number"
            placeholder="Max"
            icon="i-lucide-tag"
            class="w-full"
          >
            <template #leading>
              <span class="text-xs text-gray-500 font-semibold px-1">Rp</span>
            </template>
          </UInput>
        </div>

      </div>

      <UButton class="w-full justify-center">
        Terapkan
      </UButton>
    </div>

    <br>
    <USeparator/>
    <br>
    <!-- Filter Urutkan   -->
    <div class="mb-2">
      <p class="font-bold mb-2">
        Urutkan
      </p>

      <USelectMenu
        v-model="selectSorting"
        :items="itemSorting"
        class="w-full"
        clear
        placeholder="Pilih Urutkan"
      />
    </div>
  </UCard>
</template>

<style scoped>

</style>
