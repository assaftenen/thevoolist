<script>
export default {
  async asyncData({ $content, route }) {
    const song = await $content(
      `songs/${route.params.slug}`
    ).fetch()
    return {
      song,
    }
  },
}
</script>

<template>
  <main>
    <h1>{{ song.title }}</h1>
    <span v-for="tag in song.tags" :key="tag">{{ tag }} | </span>
    <nuxt-content
      class="prose prose-sm sm:prose lg:prose-lg xl:prose-2xl mx-auto"
      :document="song"
    />
  </main>
</template>