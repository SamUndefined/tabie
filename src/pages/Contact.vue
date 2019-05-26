<template>
    <Layout :show-logo="true">
        <Author :show-title="true" />
        <div class="contact">
        <h1>Have my contact details!</h1>
            Email: <a href="mailto:tabie2016@gmail.com">tabie2016@gmail.com</a>
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
    title: 'Contact'
  }
}
</script>

<style lang="scss">
.contact {
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
