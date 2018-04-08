<template>
  <section>
    <p>
      All my Books:
    </p>
    <nuxt-link v-for="book in books" :key="book.filename" :to="book.permalink" v-html="book.permalink"></nuxt-link>
  </section>
</template>

<script>
export default {
  async asyncData ({ app, route }) {
    return {
      books: await app.$content('/books').getAll()
    }
  }
}
</script>
