<template lang="html">
	<main id="site" class="container-fluid">

		<!-- ...... link 'back to gallery' ...... -->
		<div class="row back-to">
			<a href="/portfolio" class="d-flex">
				<i class="fas fa-long-arrow-alt-left"></i>
				Back to portfolio gallery
			</a>
		</div>

		<!-- ..... main content area ..... -->

		<div v-for="item in items" >

			<section v-if=" $route.params.id == item.id" class="row">

				<div class="col-12">

					<!-- ..... project title ..... -->
					<div class="titles">
						<h2> {{ item.title }} </h2>
					</div>

					<!-- ..... project tags ..... -->
					<div class="tags col-12 col-md-10">
						<p v-for="tags in item.tags" > {{ tags }} </p>
					</div>
				</div>

				<div class="main-content">

					<!-- ..... Slider img gallery ..... -->
					<div class="col-12 col-lg-8 image">
						<Slider />
					</div>

					<!-- ..... project text recap & description ..... -->

					<div class="col-12 col-lg-4">

					<!-- ..... short description ..... -->
					<div class="titles col-12 col-md-10">
						<h3 class="col-12"> {{ item.name }} </h3>
					</div>

					<!-- ..... long description ..... -->
					<div class="col-12 col-md-10 col-lg-8 description">
						<h4 class="col-12"> project description </h4>
						<p v-for="description in item.description" class=""> {{ description }} </p>
					</div>

					<!-- ..... project links : github / website ..... -->
					<div class="col-12 links">
						<div v-for="link in item.links" class="">
							<a :href="link.url" target="_blank">
								<i :class="link.icon"></i>
								{{ link.text }}
							</a>
						</div>
					</div>

				</div>
			</div>
		</section>
	</div>
</main>

</template>

<script>
import Slider from '~/layouts/partials/slider.vue'

export default {
	data() {
		return {
			items: [
				{
					id: 'portfolio-nuxt',
					title: 'portfolio',
					name: 'This portfolio in Nuxt.js',
					links: [
						{
							url: 'https://github.com/clairedonut/portfolio-nuxtjs',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'Learnt and used the Nuxt framework to make this portfolio!',
						'What I really appreciated using Nuxt was the hot code reloading whenever I made any changes and route anchoring was automatically generated. Making dynamic pages for the projects in the portfolio page where content is automatically adapted to IDs and URLs was a piece of cake too because Nuxt reads all the Vue files inside the Pages directory and from there builds automatically the web application router.',
						'Nuxt is straight forward to use and takes into consideration SEO best practices (like meta tags) and static site generation to help social media crawlers and search engines crawl the website'
					],
					tags: ['vue.js','nuxt.js','sass','SEO']
				},
				{
					id: 'portfolio/dentist',
					title: 'dentist',
					name: 'Dental Practice - showcase website',
					links: [
						{
							url: 'https://github.com/clairedonut/cabinet-dentaire-vuejs',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/dentist-vuejs',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'This project is a website developed for a fictional Dental practice. The essential elements of the page include: a home page, a team presentation page, an emergency page, our services page and contact form.',
						'The main focus of this project was to learn vue-cli 3 .',
						'Key elements include adding events, conditional rendering, list rendering. Animations and page transitions when the user redirects to a new page on the site, route anchoring to navigate the site and also SEO best practices such as including meta data and prerendering the pages to static html.'
					],
					tags: ['vue.js','vue-cli 3','node.js','sass','SEO']
				},
				{
					id: 'portfolio/bobuncafe',
					title: 'Bobún Café',
					name: 'Site for a fictive restaurant',
					links: [
						{
							url: 'https://github.com/clairedonut/bobun-cafe',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/bobuncafe/',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'This is a single page website for the fictive `Bobún Café`. It contains an `about us` section, `menu` section, `contact` section and images under various forms (such as a carousel).',
						'The main focus of this project was to practice vue.js',
						'Key elements include pillars of Vue.js (list rendering, conditional rendering, integration of plugins) and a few animations'
					],
					tags: ['vue.js','sass','plugins','animations']
				},
				{
					id: 'portfolio/strategies-obliques',
					title: 'Stratégies Obliques',
					name: 'Générateur de citations en Vue.js',
					links: [
						{
							url: 'https://github.com/clairedonut/strategies-obliques-vuejs',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'https://clairedonut.github.io/strategies-obliques-vuejs/',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'Ce générateur de citations m\'avait été demandé par quelqu\'un qui fait de la musique',
						'Les citations proviennent d\'un jeu de cartes ("Stratégies Obliques") conçu par Brian Eno et Peter Schmidt dans les années 1970s,',
						'Ces citations peuvent aider et guider le processus créatif et a influencé de nombreux musiciens, comme Bowie et Coldplay',
						'Une citation est générée de manière aléatoire ainsi qu\'un magnifique gradient random pour l\'arrière plan.'
					],
					tags: ['vue.js','vue']
				},
				{
					id: 'portfolio/teesandtigers-nl',
					title: 'Tees & Tigers Newsletter',
					name: 'Reproduction d\'une landing page',
					links: [
						{
							url: 'https://github.com/clairedonut/teesandtigers-NL',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/teestigersNL',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'Ce mini projet est une reproduction d\'une newsletter d\'un site de mode.',
						'Les éléments essentiels de ce projet sont l\'utilisation des Boucles et de la fonction Each() pour répèter une action (tel que la succession des images des logos). Permet de simplifier le code en évitant les répétitions de syntaxe. Le préprocesseur SASS a été utilisé pour la mise en forme de la syntaxe des styles. La mise en page est faite avec la Flex Box et les media queries pour une page responsive.'

					],
					tags: ['js','jquery'],
					url_og: 'https://news.pullandbear.com/pub/sf/ResponseForm?_ri_=X0Gzc2X%3DYQpglLjHJlTQGsXzdLhywI8XTuzeY4hb3OO9LRnp1fyUXpLjzeXKUaKc3vza42U2UzfzfzfmOVXMtX%3DYQpglLjHJlTQGuEynTcG09K551ueefKzdqWl3n7jLT58qTjMN6MlTflwPzdzcJzab2RzecO&_ei_=EnnDXGIg0i9BFbWPDwzltfjVdAfDMag2xtPNOhNroG4522IaQdTAI0iKwlGjrgLAGF4tL3lQMUSllroXh_TRDE8DCtRZsU_wnrAGFoQWx2X_W0FqY6-Ww4kYRRlzkjkeiTE_w2JexmJYQstRzdSsjbWB70Ru7Po'
				},
				{
					id: 'portfolio/teesandtigers',
					title: 'Tees & Tigers',
					name: 'Product list page of an e-commerce site',
					links: [
						{
							url: 'https://github.com/clairedonut/teesandtigers-shop-JS',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/teestigers',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'This project reproduces the product list page of a popular fashion website.',
						'The main focus of this project was to practice js and jquery.',
						'The essential elements of the page include: when clicking a brand-logo, the page will automatically update the page with content related to the brand logo. This concerns: the main banner on the top of the page, the introduction text and the products displayed.'
					],
					tags: ['js','jquery','json','bootstrap-4','jquery plugins', 'animations'],
					url_og: 'https://www.pullandbear.com/fr/homme/v%C3%AAtements/graphic-tees-c1030139007.html'
				},
				{
					id: 'portfolio/frenchstranding',
					title: 'french stranding',
					name: 'Coming Soon & Sign Up page',
					image: '/_nuxt/static/img/frenchstranding.png',
					links: [
						{
							url: 'https://github.com/clairedonut/signup-page',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://frenchstranding.fr/',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'I created a coming soon page for a French gaming community promoting Death Stranding',
						'This page integrates a Sign Up form which collects and registers emails to the associated Mail Chimp database. People registered will be notified once the website is active',
						'The email registration template\'s design from Mail Chimp were modified and adapted for the page design'
					],
					tags: ['mailchimp','email marketing']
				},
				{
					id: 'portfolio/posters',
					title: 'posters',
					name: 'Products list page in PHP & JS',
					image: '/_nuxt/static/img/posters.png',
					links: [
						{
							url: 'https://github.com/clairedonut/json-posters',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/json-posters/',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'This is a single page to practice querying arrays in PHP (data is stored in JSON format). Webpage design was replicated from Junique.com.',
						'Key elements are: a filtering & sorting system where the user can select criteria to display posters that match those criteria (type of poster, theme of poster) and sort posters by price or popularity, a search bar that returns posters based on title match etc'
					],
					tags: ['js','jquery', 'php', 'json']
				},
				{
					id: 'portfolio/kawaii-icecream',
					title: 'Kawaii Icecream',
					name: 'Instagram API, a contact form and a touch of Jquery',
					image: '/_nuxt/static/img/kawaiiicecream.png',
					links: [
						{
							url: 'https://github.com/clairedonut/kawaii-icecream',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/kawaii-icecream/',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'This is a cute one page site with an instagram feed, a few animations and a contact form',
						'Key elements are the integration of the Instagram api and a contact form made in PHP with reCAPTCHA.',
						'I practiced Bootstrap 4.0 and SASS for style properties and added a few animations on hover and click events'
					],
					tags: ['bootstrap','sass', 'php', 'jquery']
				},
				{
					id: 'portfolio/wordpress',
					title: 'wordpress blog',
					name: 'Self-hosted WordPress cms & blog',
					image: '/_nuxt/static/img/wp-blog.png',
					links: [
						{
							url: 'https://github.com/clairedonut/wordpress-blog',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/wordpress-blog/',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'I learnt about wordpress cms site integration and hosting',
						'This exercise helped me practice using the Wordpress CMS by customizing a blog\'s theme and integrating plugins (such as a contact form, slideshow, social media share buttons, a display grid with previews of articles etc).'
					],
					tags: ['wordpress', 'cms', 'plugins']
				},
				{
					id: 'portfolio/airbnb',
					title: 'airbnb',
					name: 'Reproduction of Airbnb\'s home page',
					image: '/_nuxt/static/img/airbnb.png',
					links: [
						{
							url: 'https://github.com/clairedonut/Airbnb',
							text: 'github',
							icon: 'fab fa-github'
						},
						{
							url: 'http://cookiesandwifi.ovh/airbnb',
							text: 'website',
							icon: 'fas fa-code'
						}
					],
					description: [
						'This project is a reproduction of the Airbnb homepage in responsive design',
						'This is one of my first projects. It helped me learn about media queries, the mobile-first approach and optimising image formats',
						'Later on, this project was updated to also include jquery (the dropdown nav in for mobile) and plugins (the search bar)',
						'Other earlier projects are also on my github'
					],
					tags: ['responsive design', 'media queries', 'flexbox', 'jquery', 'plugins' ]
				}
			]
		}
	},
	components: {
		Slider
	}
}
</script>

<style lang="scss">

#site {
	padding-top: 3em;
	margin-bottom: 3em;

	.col-12 {
		margin: 1em auto;
	}

	p {
		margin: 1em 0;
	}

	figure {
		margin-bottom: 5em;
	}

	h4 {
		font-size: 10px;
		text-transform: uppercase;
		letter-spacing: 2px;
		margin-top: 3em;
		margin-right: 1em;
		text-align: center;
	}


	/* ******* project title ******* */
	.titles {
		h2, h3 {
			text-align: center;
			padding: 0;
		}

		h2 {
			margin-bottom: 0.3em;
		}

		h3 {
			color: #484848;
			letter-spacing: 2px;
			text-transform: lowercase;
			font-size: 1em;
		}
	}

	/* ******* project links : github /  website ******* */

	.links {
		display: -webkit-box;
		display: -ms-flexbox;
		display: flex;
		-ms-flex-wrap: wrap;
		    flex-wrap: wrap;
		-webkit-box-pack: center;
		    -ms-flex-pack: center;
		        justify-content: center;
		-webkit-box-align: baseline;
		    -ms-flex-align: baseline;
		        align-items: baseline;


		margin: 2em auto;
		a {
			margin: 2em  ;
			cursor: pointer;
			font-size: 11px;
			text-transform: uppercase;
			letter-spacing: 2px;
			font-weight: 600;
		}
		i {
			margin: auto 0.5em;
			font-size: 13px;
		}
		a, i {
			padding-bottom: 5px;
		}
	}

	/* ******* project tags ******* */

	.tags {
		display: -webkit-box;
		display: -ms-flexbox;
		display: flex;
		-ms-flex-wrap: wrap;
		    flex-wrap: wrap;
		-webkit-box-pack: center;
		    -ms-flex-pack: center;
		        justify-content: center;
		-webkit-box-align: baseline;
		    -ms-flex-align: baseline;
		        align-items: baseline;

		margin: 1em auto 2em;
		h4 {
			margin-top: 1em;
			margin-bottom: 1em;
		}
		p {
			margin-right: 1em;
			font-weight: bold;
			text-transform: lowercase;
			letter-spacing: 1px;

			height: 34px;
			padding: 0 20px;
			line-height: 34px;
			color: #49c5b6;
			overflow: hidden;
			z-index: 1;
			-webkit-transition: all 0.3s ease-in-out;
			-o-transition: all 0.3s ease-in-out;
			transition: all 0.3s ease-in-out;

			&:hover {
				cursor: default;
				text-decoration: none;
			}
		}
	}

	/* ******* project description ******* */

	.description {
		text-align: left;
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
		margin-top: 3em;
		p {
			margin: 1em 2em;
			font-size: 1em;
			text-align: left;
			width: 90%;
		}
	}

	.image {
		max-height: 500px;
		overflow: hidden;
		padding-bottom:40em;
		margin-top: 5em;
		margin-bottom: 0;

		img {
			width: 100%;
			height: auto;
		}

	}

	/* ******* 'back to gallery' link ******* */

	.back-to {
		text-transform: uppercase;
		letter-spacing: 2px;
		font-size: 12px;
		margin: 2.5em 2em;

		i {
			font-size: 20px;
			margin-right: 5px;
		}

		.d-flex {
			display: -webkit-box;
			display: -ms-flexbox;
			display: flex;
			-webkit-box-align: center;
			    -ms-flex-align: center;
			        align-items: center;
			-webkit-box-pack: start;
			    -ms-flex-pack: start;
			        justify-content: flex-start;
		}

		a:hover {
			color: #ED6B86;
		}
	}
}
</style>
