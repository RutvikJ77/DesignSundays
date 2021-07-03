<template>
	<div class="author">
		<g-image alt="Author image" class="author__image" src="~/assets/images/logo.jpg" width="250" height="250" />

		<h1 v-if="showTitle" class="author__site-title">
			{{ $static.metadata.siteName }}
		</h1>

		<p class="author__intro">
			By ~ Rutvik J
		</p>
		
		<p class="author__links">
			
			<a href="https://twitter.com/Rutvikstwt">Twitter</a>
			<a href="https://behance.net/rutvikj">Bēhance</a>
			<a href="https://github.com/RutvikJ77">GitHub</a>
			
		</p>

	</div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import { icons } from "@/assets/ionicons";
export default {
	props: ['showTitle'],
	data(){
		return {
			ionicons: icons
		};
	}
}
</script>

<style lang="scss">
.author {
	margin: 0 auto;
	max-width: 500px;
	text-align: center;
	padding-bottom: calc(var(--space) / 2);

	&__image {
		border-radius: 100%;
		width: 125px;
		height: 125px;
		margin-bottom: 1em;
	}

	&__intro {
		opacity: .8;
	}

	&__site-title {
		margin: 0 auto;
		font-size: 1.5em;
		max-width: 400px;
	}

	&__links {
		margin-top: -.5em;
		a {
			margin: 0 .5em;
		}
	}
}
</style>
