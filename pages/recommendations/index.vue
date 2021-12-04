<script>
export default {
  data: () => ({
    recommendations: [],
  }),
  async created() {
    this.recommendations = await this.$content('recommendations').fetch()
  },
}
</script>
<template>
  <main>
    <h1>My recommendations</h1>
    <ul>
      <li v-for="recommendation in recommendations" :key="recommendation.slug">
        <p>{{ recommendation.title }}</p>
        <h2>
          <nuxt-link :to="`/recommendations/${recommendation.slug}`">{{
            recommendation.slug
          }}</nuxt-link>
        </h2>
      </li>
    </ul>
  </main>
</template>
