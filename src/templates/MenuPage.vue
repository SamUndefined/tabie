<template>
    <Layout :show-logo="true">
        <Author :show-title="true" />

        <div class="page">
          <h1>{{$page.page.title}}</h1>
          <div v-html="$page.page.content"></div>
        </div>
    </Layout>
</template>

<page-query>
query MenuPage ($path: String!) {
  page: menuPage (path: $path) {
    title
    content
  }
}
</page-query>

<script>
import Author from '~/components/Author.vue'

export default {
  components: {
    Author,
  },
  metaInfo () {
    return {
      title: this.$page.page.title
    }
  },
}
</script>

<style <style lang="scss">
.page {
    margin: auto;
    padding: 1.5rem 1rem;
    border: 1px solid rgba(100, 100, 100, .25);
    border-radius: var(--radius) var(--radius) 0 0;

    h1 {
      text-align: center
    }

    @media screen and (min-width: 600px) {
        max-width: 80%;
    }

    @media screen and (min-width: 768px) {
        max-width: 50%;
    }
}
</style>
