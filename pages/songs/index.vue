<script>
export default {

  async asyncData({$content, route}) {
    const songs = await $content('songs').fetch();
    return ({
      songs
    })
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
