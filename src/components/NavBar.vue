<script setup>
  import { ref } from 'vue'
  const brand = ref('🏭 Company Directory')
</script>

<template>
  <nav>
    <div class="wrapper">
      <RouterLink :to="{name:'home'}" class="brand">
        <span class="brand-title">{{ brand }}</span>
      </RouterLink>
      <div class="menu">
        <a href="#" class="menu-items">Departments</a>
        <a href="#" class="menu-items">Settings</a>
        <a href="#" class="menu-login">Sign off</a>
      </div>
    </div>
  </nav>
</template>

<style scoped lang="postcss">
  nav {
    @apply h-10 bg-gray-800 text-white;
    .wrapper {
      @apply container mx-auto flex w-full items-center justify-between;
      .brand {
        &-title {
          @apply text-3xl font-semibold text-gray-400;
        }
      }
      .menu {
        @apply flex gap-2;
        &-items {
          @apply rounded-md px-4 py-2 text-gray-400 hover:bg-gray-400 hover:text-black;
        }
        &-login {
          @apply rounded-md px-4 py-2 text-gray-400 hover:bg-red-600 hover:text-black;
        }
      }
    }
  }
</style>
