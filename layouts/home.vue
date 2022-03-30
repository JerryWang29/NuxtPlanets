<template>
  <div class="container">
    <div>
      <Nuxt />

      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/about">about</NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
}
</script>
