<template>
  <div class="container">
    <div>
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/about">about</NuxtLink>
      <Nuxt />
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  // Global page headers: https://go.nuxtjs.dev/config-head
  head: {
    title: 'Nuxt mission',
    htmlAttrs: {
      lang: 'en',
    },
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        hid: 'description',
        name: 'description',
        content: 'A mission to explore the Jamstack using Nuxt',
      },
      { name: 'format-detection', content: 'telephone=no' },
    ],
    link: [{ rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }],
  },
}
</script>
