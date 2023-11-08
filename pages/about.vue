<template>
  <div>
    <p>works here too</p>
    <nuxt-link :to="{ name: 'index' }">try on index</nuxt-link>
    <pre>{{ data }}</pre>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const { data } = await $axios.get(
      'https://jsonplaceholder.typicode.com/posts/2'
    )
    return { data }
  },
  mounted() {
    console.log('yes, it does work too', this.data)
  },
}
</script>
