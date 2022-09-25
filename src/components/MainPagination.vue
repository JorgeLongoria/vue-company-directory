<script setup>
  import { ref } from 'vue'
  const pages = ref(5)
  const activePage = ref(4)
  const prevPage = () => {
    if (activePage.value > 1) {
      activePage.value--
    }
  }
  const nextPage = () => {
    if (activePage.value < pages.value) {
      activePage.value++
    }
  }
</script>

<template>
  <div class="pagination">
    <button class="action" :disabled="activePage === 1" @click="prevPage">Prev</button>
    <button class="page" v-for="page in pages" :key="page" :class="page === activePage ? 'active' : ''" @click="activePage = page">
      {{ page }}
    </button>
    <button class="action" :disabled="activePage === pages" @click="nextPage">Next</button>
  </div>
</template>

<style lang="postcss" scoped>
  .pagination {
    @apply flex justify-center gap-4;
    .action {
      @apply rounded-md bg-gray-200 p-2 font-medium text-gray-800 shadow-md hover:bg-gray-300 disabled:text-gray-500 hover:disabled:bg-gray-200;
    }
    .page {
      @apply rounded-md bg-gray-200 p-2 font-medium text-gray-800 shadow-md hover:bg-gray-300;
      &.active {
        @apply bg-red-600 text-gray-200 hover:bg-gray-800;
      }
    }
  }
</style>