<template>
    <Layout :show-logo="true">
        <Author :show-title="true" />

        <div class="about">
          <h1>{{$page.about.edges[0].node.title}}</h1>
          <div v-html="$page.about.edges[0].node.content"></div>
        </div>
    </Layout>
</template>

<page-query>
query about {
  about: allAbout {
    edges {
      node {
        title
        content
      }
    }
  }
}
</page-query>

<script>
import Author from '~/components/Author.vue'

export default {
  components: {
    Author,
  },
  metaInfo: {
    title: 'About'
  },
}
</script>

<style <style lang="scss">
.about {
    margin: auto;
    background-color: white;
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
