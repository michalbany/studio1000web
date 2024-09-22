<script setup lang="ts">
const config = useRuntimeConfig();

useHead({
  titleTemplate: '%s | ' + config.public.appName,
})

</script>
<template>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>
