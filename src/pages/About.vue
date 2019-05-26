<template>
    <Layout :show-logo="true">
        <Author :show-title="true" />

        <div class="about">
            <h1>About</h1>
            <p>This page is under construction.</p>
        </div>
    </Layout>
</template>

<script>
import Author from '~/components/Author.vue'

export default {
  components: {
    Author,
  },
  metaInfo: {
    title: 'About'
  }
}
</script>

<style <style lang="scss">
.about {
    margin: auto;
    text-align: center;
    background-color: white;
    padding: 3rem 0;
    border: 1px solid rgba(100, 100, 100, .25);
    border-radius: var(--radius) var(--radius) 0 0;

    @media screen and (min-width: 600px) {
        max-width: 80%;
    }

    @media screen and (min-width: 768px) {
        max-width: 50%;
    }
}
</style>
