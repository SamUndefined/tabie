<template>
    <Layout>
        <div class="not-found">
            <h1>Page Not Found</h1>
            <h3>Welcome to the off-beaten path!</h3>
            <p>Or rather, welcome to <em><strong>no</strong></em> path... oops.</p>
        </div>
    </Layout>
</template>

<script>
export default {
    name: 'NotFound',
    metaInfo: {
        title: '404'
    }
}
</script>

<style lang="scss">
.not-found {
    text-align: center;
    margin-top: 3rem;
    margin-bottom: 10rem;
}
</style>

