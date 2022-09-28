<script setup>
  import { ref } from 'vue'
  import { useAuth } from '@/composables/useAuth'

  const { isAuthenticated, logout, user } = useAuth()

  const brand = ref(import.meta.env.VITE_APP_NAME)
</script>

<template>
  <nav>
    <div class="wrapper">
      <RouterLink :to="{ name: 'Home' }" class="brand">
        <span class="brand-title">{{ brand }}</span>
      </RouterLink>
      <div class="menu">
        <div v-if="isAuthenticated">
          <i v-show="isAuthenticated" class="px-2 py-4 text-yellow-300">Welcome {{ user.name }}</i>
          <RouterLink :to="{ name: 'Settings' }" href="#" class="menu-items">Settings</RouterLink>
          <button href="#" class="menu-logout" @click="logout">Logout</button>
        </div>
        <div v-else>
          <RouterLink :to="{ name: 'Login' }" href="#" class="menu-login">Login</RouterLink>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped lang="postcss">
  nav {
    @apply h-20 bg-gray-800;
    .wrapper {
      @apply container mx-auto flex w-full items-center justify-between;
      .brand {
        &-title {
          @apply text-4xl font-semibold text-white;
        }
      }
      .menu {
        @apply flex gap-2;
        div {
          @apply py-2;
        }
        &-items {
          @apply rounded-md bg-gray-400 px-4 py-2 text-black hover:bg-gray-200;
        }
        &-login {
          @apply mx-2 rounded-md bg-green-600 px-4 py-2 text-black hover:bg-green-300;
        }
        &-logout {
          @apply mx-2 rounded-md bg-red-600 px-4 py-2 text-black hover:bg-red-300;
        }
      }
    }
  }
</style>
