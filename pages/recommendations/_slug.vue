<script>
export default {
  async asyncData({ $content, route }) {
    const recommendation = await $content(`recommendations/${route.params.slug}`).fetch();
    return {
      recommendation
    };
  }
};
</script>

<template>
  <main>
    <h1>{{ recommendation.title }}</h1>
    <span v-for="tag in recommendation.tags" :key="tag">{{ tag }} | </span>
    <nuxt-content :document="recommendation" />
  </main>
</template>