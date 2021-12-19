<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://iwata-test.microcms.io/api/v1/nuxt-blog1/${params.slug}`,
      {
        headers: { 'X-MICROCMS-API-KEY': 'a782da27f43144568aea7ca6a46a8b3d3022' }
      }
    )
    return data
  }
}
</script>