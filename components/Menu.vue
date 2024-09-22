<template>
  <div class="hidden sm:ml-6 sm:block">
    <div class="flex space-x-4">
      <NuxtLink
        to="/"
        :class="isActiveRoute('/') ? 'rounded-md bg-gray-900 px-3 py-2 text-sm font-medium text-white' : 'rounded-md px-3 py-2 text-sm font-medium text-gray-300 hover:bg-gray-700 hover:text-white'"
      >
        Home
      </NuxtLink>
      <NuxtLink
        to="/team"
        :class="isActiveRoute('/team') ? 'rounded-md bg-gray-900 px-3 py-2 text-sm font-medium text-white' : 'rounded-md px-3 py-2 text-sm font-medium text-gray-300 hover:bg-gray-700 hover:text-white'"
      >
        Náš tým
      </NuxtLink>
      <NuxtLink
        to="/projects"
        :class="isActiveRoute('/projects') ? 'rounded-md bg-gray-900 px-3 py-2 text-sm font-medium text-white' : 'rounded-md px-3 py-2 text-sm font-medium text-gray-300 hover:bg-gray-700 hover:text-white'"
      >
        Projekty
      </NuxtLink>
      <NuxtLink
        to="/contact"
        :class="isActiveRoute('/contact') ? 'rounded-md bg-gray-900 px-3 py-2 text-sm font-medium text-white' : 'rounded-md px-3 py-2 text-sm font-medium text-gray-300 hover:bg-gray-700 hover:text-white'"
      >
        Kontakty
      </NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();

// Funkce na kontrolu, zda je odkaz aktivní
const isActiveRoute = (to: string) => {
  return computed(() => route.path === to).value;
};
</script>
