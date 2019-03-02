<template>
	<div class="author">

		<g-image alt="Author image" class="author__image" src="~/assets/images/author.jpg" width="180" height="180" blur="5" />

		<h1 v-if="showTitle" class="author__site-title">
			<!-- todo: get title from a netlify controlled piece of data -->
			{{ $static.metaData.siteName }}
		</h1>

		<p class="author__intro">
			An awesome new blog website for an awesome little sister!
		</p>

		<p class="author__links">
			<a href="//twitter.com/gridsome">Twitter</a>
			<a href="//github.com/gridsome/gridsome-starter-blog">Youtube</a>
		</p>

	</div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<script>
export default {
	props: ['showTitle']
}
</script>

<style lang="scss">
.author {
	margin: 0 auto;
	max-width: 500px;
	text-align: center;
	padding: 0 0 calc(var(--space) / 2) 0;

	&__image {
		border-radius: 100%;
		width: 90px;
		height: 90px;
		margin-bottom: 1em;
	}

	&__intro {
		opacity: .8;
	}

	&__site-title {
		font-size: 1.5em;
	}

	&__links {
		margin-top: -1em;
		margin-bottom: 0;
		font-size: 0.75rem;
		a {
			margin: 0 0.3rem;
		}
	}
}
</style>