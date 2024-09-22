<template>
  <div class="sm:hidden" id="mobile-menu">
    <div class="space-y-1 px-2 pb-3 pt-2">
      <NuxtLink
        to="/"
        :class="isActiveRoute('/') ? 'block rounded-md bg-gray-900 px-3 py-2 text-base font-medium text-white' : 'block rounded-md px-3 py-2 text-base font-medium text-gray-300 hover:bg-gray-700 hover:text-white'"
      >
        Home
      </NuxtLink>
      <NuxtLink
        to="/team"
        :class="isActiveRoute('/team') ? 'block rounded-md bg-gray-900 px-3 py-2 text-base font-medium text-white' : 'block rounded-md px-3 py-2 text-base font-medium text-gray-300 hover:bg-gray-700 hover:text-white'"
      >
        Náš tým
      </NuxtLink>
      <NuxtLink
        to="/projects"
        :class="isActiveRoute('/projects') ? 'block rounded-md bg-gray-900 px-3 py-2 text-base font-medium text-white' : 'block rounded-md px-3 py-2 text-base font-medium text-gray-300 hover:bg-gray-700 hover:text-white'"
      >
        Projekty
      </NuxtLink>
      <NuxtLink
        to="/contact"
        :class="isActiveRoute('/contact') ? 'block rounded-md bg-gray-900 px-3 py-2 text-base font-medium text-white' : 'block rounded-md px-3 py-2 text-base font-medium text-gray-300 hover:bg-gray-700 hover:text-white'"
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
