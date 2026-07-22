<script setup lang="ts">

const books = ref([
  { id: 1, title: 'Belajar Nuxt 3 dari Dasar', price: 'Rp 120.000', author: 'Budi Santoso', rating: 4.8, reviewsCount: 120 },
  { id: 2, title: 'Mastering Tailwind CSS', price: 'Rp 95.000', author: 'Siti Aminah', rating: 4.9, reviewsCount: 85 },
  { id: 3, title: 'Arsitektur Perangkat Lunak', price: 'Rp 150.000', author: 'Joko Widodo', rating: 4.7, reviewsCount: 64 },
  { id: 4, title: 'Pemrograman TypeScript', price: 'Rp 110.000', author: 'Dewi Lestari', rating: 5.0, reviewsCount: 210 },
  { id: 5, title: 'Fullstack Developer Guide', price: 'Rp 175.000', author: 'Ahmad Fauzi', rating: 4.6, reviewsCount: 42 },
])
</script>

<template>
  <div class="px-2">
    <p class="text-2xl font-bold">Katalog Buku</p>
    <span class="text-xs">Menampilkan 1 - 8 dari 24 buku</span>


  </div>
  <div class="w-full py-2">
    <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-4">

      <!-- Memanfaatkan komponen UCard dari Nuxt UI -->
      <UCard
        v-for="book in books"
        :key="book.id"
        class="flex flex-col justify-between hover:ring-2 hover:ring-primary transition-all duration-300 hover:-translate-y-1 shadow-sm hover:shadow-xl cursor-pointer"
        :ui="{ body: 'flex flex-col justify-between h-full p-4 sm:p-4' }"
      >
        <!-- Bagian Cover Buku -->
        <div class="w-full h-40 bg-gray-100 dark:bg-gray-800 rounded-md mb-3 flex items-center justify-center text-gray-400 text-xs">
          Cover Buku
        </div>

        <!-- Informasi Buku -->
        <div class="mb-4">
          <h3 class="font-semibold text-sm text-gray-900 dark:text-white line-clamp-2 mb-1">
            {{ book.title }}
          </h3>
          <p class="text-xs text-gray-500">
            {{ book.author }}
          </p>
        </div>

        <!-- Harga -->
        <div class="font-bold text-primary text-sm mt-auto">
          {{ book.price }}
        </div>

        <div class="flex items-center gap-1.5 text-xs text-gray-600 dark:text-gray-400">
          <!-- Ikon Bintang menggunakan Nuxt UI -->
          <div class="flex text-amber-400">
            <UIcon name="i-lucide-star" class="w-3.5 h-3.5 fill-current" />
          </div>

          <span class="font-medium text-gray-700 dark:text-gray-300">
              {{ book.rating }}
            </span>
          <span class="text-gray-400">
              ({{ book.reviewsCount }})
            </span>
        </div>
      </UCard>

    </div>
  </div>
</template>

<style scoped>

</style>
