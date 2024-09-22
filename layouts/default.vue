<template>
  <div class="bg-slate-900 text-white selection:bg-red-500 selection:text-white">
    <div class="min-h-screen">
      <NavBar class="mb-8 sticky top-0 z-50"/>
      <main class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8 pb-16">
        <slot />
      </main>
    </div>
  </div>
</template>
