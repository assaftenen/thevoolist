<script>
export default {
  data: () => ({
    songs: [],
  }),
  async created() {
    this.songs = await this.$content('songs').fetch()
  },
}
</script>
<template>
  <main>
    <h1>Musics Hits</h1>
    <ul>
      <li v-for="song in songs" :key="song.slug">
        <p>{{ song.title }}</p>
        <h2>
          <nuxt-link :to="`/songs/${song.slug}`">{{
            song.slug
          }}</nuxt-link>
        </h2>
      </li>
    </ul>
  </main>
</template>
