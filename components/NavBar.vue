<template>
  <nav class="bg-slate-800">
    <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
      <div class="relative flex h-16 items-center justify-between">
        <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
          <!-- Mobile menu button-->
          <button
            @click="isMenuOpen = !isMenuOpen"
            type="button"
            class="relative inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
            aria-controls="mobile-menu"
            aria-expanded="false"
          >
            <Icon name="lucide:menu" class="block h-6 w-6" v-if="!isMenuOpen" />
            <Icon name="lucide:x" class="block h-6 w-6" v-if="isMenuOpen" />
          </button>
        </div>
        <div
          class="flex flex-1 items-center justify-center sm:items-stretch sm:justify-start"
        >
          <AppLogoWhite class="w-24" />
          <Menu />
        </div>
        <div
          class="absolute inset-y-0 right-0 flex items-center pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0"
        >
          <UiButton size="sm"
            ><Icon name="lucide:party-popper" />Přispět</UiButton
          >
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition
      enter-active-class="transition ease-out duration-100 transform"
      enter-from-class="opacity-0 scale-95"
      enter-to-class="opacity-100 scale-100"
      leave-active-class="transition
        ease-in duration-75 transform"
      leave-from-class="opacity-100 scale-100"
      leave-to-class="opacity-0 scale-95"
    >
      <ResponsiveMenu v-if="isMenuOpen" />
    </Transition>
  </nav>
</template>

<script setup lang="ts">
const isMenuOpen = ref(false);
</script>
