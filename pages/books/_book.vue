<template>
  <section>
    <p>
      My Book:
    </p>
    <p v-html="book.title"></p>
    <div v-html="book.body"></div>
  </section>
</template>
<script>
export default {
  async asyncData ({ app, route }) {
    return {
      book: await app.$content('/books').get(route.path)
    }
  }
}
</script>
