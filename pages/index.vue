<template>
  <div>
    <h1>The Voo List</h1>
    <NuxtLink to="/songs"
      >Songs</NuxtLink>
  </div>

</template>

<script>
export default {
  mounted() {
    // eslint-disable-next-line no-console
    console.log(this.$content);
  }
};
</script>