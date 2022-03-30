<template>
  <div class="container">
    <div>
      <img :src="planet.image" alt="" />
      <h1 class="title">{{ planet.title }}</h1>
      <PlanetsList />
    </div>
  </div>
</template>

<script>
export default {
  transition: 'bounce',
  //   name: 'IndexPage',
  async asyncData({ params }) {
    const planet = await fetch(
      `https://api.nuxtjs.dev/planets/${params.slug}`
    ).then((res) => {
      if (res.ok) {
        return res.json()
      }
      throw new Error(res.status)
    })
    return { planet }
  },

  head() {
    return {
      title: this.planet.title,
      htmlAttrs: {
        lang: 'en',
      },
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        {
          hid: 'description',
          name: 'description',
          content: this.planet.description,
        },
        { name: 'format-detection', content: 'telephone=no' },
      ],
      link: [{ rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }],
    }
  },
}
</script>
