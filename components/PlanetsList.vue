<template>
  <div>
    <p v-if="$fetchState.pending">Fetching planet...</p>
    <p v-else-if="$fetchState.error">Error while fetching planets</p>
    <ul>
      <li v-for="planet in planets" :key="planet.slug">
        <NuxtLink :to="planet.slug">
          {{ planet.title }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  layout: 'home',
  data() {
    return {
      planets: [],
    }
  },

  async fetch() {
    this.planets = await fetch('https://api.nuxtjs.dev/planets').then((res) =>
      res.json()
    )
  },
}
</script>
