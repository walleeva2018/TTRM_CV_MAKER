<script lang="ts" setup>
const localePath = useLocalePath()
</script>

<template>
  <h1>
    <NuxtLink :to="localePath('/')" class="bg-none font-bold text-fl-lg font-logo uppercase tracking-widest"
      active-class="bg-none">
      <img height="200" width="100" src="../../assets/werhere_nl_logo.jpeg" />
    </NuxtLink>
  </h1>
</template>
