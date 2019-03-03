<template>
	<div class="author">

		<g-image alt="Author image" class="author__image" src="~/assets/images/tabie.jpg" width="180" height="180" blur="5" />

		<h1 v-if="showTitle" class="author__site-title">
			<!-- todo: get title from a netlify controlled piece of data -->
			{{ $static.metaData.siteName }}
		</h1>

		<p class="author__links">
			<a href="//youtube.com/channel/UCYJUWAid0wsbsvqt_XYevww">
				<g-image immediate="true" alt="Youtube Icon" src="/icons/youtube.svg" />
			</a>
			<a href="//instagram.com/tabie2016">
				<g-image immediate="true" alt="Instagram Icon" src="/icons/instagram.svg" />
			</a>
			<a href="//pinterest.com/Tabie2016/">
				<g-image immediate="true" alt="Pinterest Icon" src="/icons/pinterest.svg" />
			</a>
		</p>

		<p class="author__quote">
			A small act is worth a million thoughts. 
			<em class="author__quote__author"> —Ai Weiwei</em>
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

	&__quote {
		opacity: .8;
		&__author {
			opacity: .7;
		}
	}

	&__site-title {
		font-size: 1.5em;
		margin-top: -0.5rem;
		margin-bottom: 1.5rem;
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