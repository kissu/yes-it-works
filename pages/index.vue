<template>
  <div>
    <p>works here so far</p>
    <nuxt-link :to="{ name: 'about' }">try on about</nuxt-link>
    <pre>{{ data }}</pre>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const { data } = await $axios.get(
      'https://jsonplaceholder.typicode.com/posts/1'
    )
    return { data }
  },
  mounted() {
    console.log('works here', this.data)
  },
}
</script>
