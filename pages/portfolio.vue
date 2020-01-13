<template lang="html">

	<main id="portfolio" class="container">

		<section class="row">

			<div id="projects-display" class="">
				<a :href="item.url" v-for="item in items" class="col-6 col-lg-4 project-image">
						<figure class="">
							<img :src="item.image" class="" alt="">
						</figure>
						<div class="text">
							<h2> {{ item.name }} </h2>
						</div>
				</a>

				<!-- <div v-for="item in items" class="col-6 col-lg-4 project-image">
						<nuxt-link :to="item.url" >
						<figure class="">
							<img :src="item.image" class="" alt="">
						</figure>
						<div class="text">
							<h2> {{ item.name }} </h2>
						</div>
						</nuxt-link>
				</div> -->

				<!-- <nuxt-link :to="item.url" v-for="item in items"><h2> {{ item.name }} </h2></nuxt-link> -->

			</div>

		</section>


	</main>

</template>

<script>

export default {
	head() {
		return {
			// title: 'Claire Portfolio',
			meta: [
				// { name: 'description', content: 'All my Portfolio projects' }
			]
		}
	},
	data() {
		return {
			title: 'Portfolio',
			items: [
				{
					name: 'This Portfolio',
					image: '/img/portfolio.png',
					url: '/portfolio-projects/portfolio-nuxt'
				},
				{
					name: 'Showcase Dental practice website',
					image: '/img/dentist-2.png',
					tags: ['vue.js','vue-cli 3','node.js','sass','SEO'],
					url: '/portfolio-projects/dentist'
				},
				{
					name: 'Bobún Café',
					image: '/img/bobuncafe-5.png',
					tags: ['vue.js','vue-cli 3','node.js','sass','SEO'],
					url: '/portfolio-projects/bobuncafe'
				},
				{
					name: 'Tees & Tigers',
					image: '/img/teesandtigers.png',
					tags: ['vue.js','vue-cli 3','node.js','sass','SEO'],
					url: '/portfolio-projects/teesandtigers'
				},
				{
					name: 'Quotes generator',
					image: '/img/strategiesobliques.png',
					url: '/portfolio-projects/strategies-obliques'
				},
				{
					name: 'Tees & Tigers LP',
					image: '/img/teestiger-nl.png',
					url: '/portfolio-projects/teesandtigers-nl'
				},
				{
					name: 'french stranding',
					image: '/img/frenchstranding.png',
					url: '/portfolio-projects/frenchstranding'
				},
				{
					name: 'posters json',
					image: '/img/posters.png',
					url: '/portfolio-projects/posters'

				},
				{
					name: 'Wordpress CMS',
					image: '/img/wp-blog.png',
					url: '/portfolio-projects/wordpress'
				},
				{
					name: 'kawaii icecream',
					image: '/img/kawaiiicecream.png',
					url: '/portfolio-projects/kawaii-icecream'
				},
				{
					name: 'Airbnb homepage',
					image: '/img/airbnb-desktop.png',
					url: '/portfolio-projects/airbnb'
				}
			]
		}
	},
	components: {
	}
}
</script>

<style lang="scss">

#portfolio {

	section {
		display: -webkit-box;
		display: -ms-flexbox;
		display: flex;
		-webkit-box-pack: center;
		    -ms-flex-pack: center;
		        justify-content: center;
		-webkit-box-align: center;
		    -ms-flex-align: center;
		        align-items: center;
		-ms-flex-wrap: wrap;
		    flex-wrap: wrap;

		padding-top: 6em;
	}

	h1 {
		text-align: center;
		margin: 3em 0;
	}



	.project-image {
		cursor: pointer;

		display: -webkit-box;

		display: -ms-flexbox;

		display: flex;
		-webkit-box-orient: vertical;
		-webkit-box-direction: normal;
		    -ms-flex-direction: column;
		        flex-direction: column;
		-webkit-box-align: center;
		    -ms-flex-align: center;
		        align-items: center;
		-webkit-box-pack: center;
		    -ms-flex-pack: center;
		        justify-content: center;

		margin: 0;
		overflow: hidden;

		figure {
			overflow: hidden;
			position: relative;
			width: 100%; /* The size you want */

			&:after {
				content: "";
				display: block;
				padding-bottom: 100%;
			}

			img {
				position: absolute; /* Take your picture out of the flow */
				top: 0;
				bottom: 0;
				left: 0;
				right: 0; /* Make the picture taking the size of it's parent */
				width: 100%; /* This if for the object-fit */
				height: 100%; /* This if for the object-fit */
				-o-object-fit: cover;
				   object-fit: cover; /* Equivalent of the background-size: cover; of a background-image */
				-o-object-position: top;
				   object-position: top;

				&:hover {
					opacity: 0.8;
					-webkit-transition: opacity .3s ease-out;
					-o-transition: opacity .3s ease-out;
					transition: opacity .3s ease-out;
				}
			}

		}

	}

	.tags {
		display: -webkit-box;
		display: -ms-flexbox;
		display: flex;
		-ms-flex-wrap: nowrap;
		    flex-wrap: nowrap;

		margin: 1em 0;
	}

	.tag {
		padding: 1em 0.2em 1em 0 ;
		margin-right: 0.5em;

		text-transform: lowercase;
		color: grey;
		font-weight: 700;
	}

	.text {
		padding: 2em auto;
		margin: 2em auto;

		h2 {
			font-size: 14px;
			line-height: 1.6em;
			text-transform: uppercase;
			text-decoration: none;
			letter-spacing: .06em;
			text-align: center;
			font-weight: 300;
			font-style: normal;
			color: #404040;

		}

		.links {
			font-size: 0.8em;
			text-transform: lowercase;
			font-weight: 400;
			font-style: normal;
		}
	}

}

#projects-display {
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	-ms-flex-wrap: wrap;
	    flex-wrap: wrap;
}
</style>
