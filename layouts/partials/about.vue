<template>

	<section id="about" class="row d-flex">

		<!-- ..................... introduction text ..................... -->
		<div class="offset-1 col-10 col-md-5 col-lg-5 text">
			<h2> {{ title }} </h2>
			<h2 class="typeit"></h2>
			<p v-for="item in items"> {{ item }}</p>

			<!-- ...... Links to portfolio page / download CV / skills area ...... -->
			<p>My portfolio with my latest projects: 	<a href="http://cookiesandwifi.ovh/portfolio" class="link">cookiesandwifi.ovh/portfolio</a></p>

			<aside class="row">
				<div class="col-6">
					<i class="far fa-file-pdf"></i>
					<a :href="fileURL" download class="document-pdf">Download resume</a>
				</div>
				<div class="col-6">
					<i class="fas fa-plus"></i>
					<a href="#skills" class="skills-link">View skills</a>
				</div>

			</aside>

		</div>

		<!-- ..................... profile image ..................... -->
		<div class="offset-1 col-10 offset-md-0 col-md-5 offset-lg-1 col-lg-4">
			<figure class="">
				<img src="@/static/img/profile.jpg" alt="" class="">
			</figure>
		</div>


	</section>

</template>

<script>

export default {
	head() {
		return {
			title: 'About page',
			meta: [
				{ name: 'description', content: 'This is an about page about Claire' }
			]
		}
	},
	data() {
		return {
			title: 'Hi, I\'m Claire',
			image: '@/static/img/profile.jpg',
			fileURL: '/docs/CV_EN-FR_FrontEnd-Dev_Claire.pdf',
			items: [
				'Intensive training in web developement & personal projects helped me gain various technical skills to build websites.',
				'I specialise in the front-end side of web developement because I love planning and working on the design part of a project but also enjoy getting involved in the technical side to build a beautiful and user-friendly UI.',
				'Prior to web-developement, I was in web-marketing. I have a background in digital marketing following over 5 years of working and studying in different international environements and countries.'
			]
		}
	}
}
</script>

<style lang="scss">

@mixin flex-row($horizontal,$vertical) {
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	-webkit-box-orient: horizontal;
	-webkit-box-direction: normal;
	-ms-flex-direction: row;
	flex-direction: row;
	-webkit-box-pack: $horizontal;
	-ms-flex-pack: $horizontal;
	justify-content: $horizontal;
	-webkit-box-align: $vertical;
	-ms-flex-align: $vertical;
	align-items: $vertical;
}

html {
	scroll-behavior: smooth;
}

#about {
	padding: 100px 0 0 0;
	padding-bottom: 10px !important;

	.text {
		margin-bottom: 3em;
	}

	h2 {
		font-size: 2.5em;
		margin-bottom: 1em;
	}

	div {
		padding: 17px;
		margin-top: 2em;
	}

	figure {
		@include flex-row(center,flex-start);
	}

	figure {
		overflow: hidden;
		position: relative;
		width: 100%; /* The size you want */
		height: auto;

		&:after {
			content: "";
			display: block;
			padding-bottom: 100%; /* The padding depends on the width, not on the height, so with a padding-bottom of 100% you will get a square */
		}

		img {
			position: absolute; /* Take your picture out of the flow */
			width: 80%; /* This if for the object-fit */
			height: 80%; /* This if for the object-fit */
			-o-object-fit: cover;
			   object-fit: cover; /* Equivalent of the background-size: cover; of a background-image */
			-o-object-position: top;
			   object-position: top;
		}
	}

	p, a {
		letter-spacing: 0.5px;
		font-weight: 400;
		line-height: 1.6em;
		margin: 0 0 1.6em;
	}

	.link {
		border-bottom: 2px solid #1C7C54 !important;
		padding-bottom: 2px;
		font-weight: bold;
		&:hover {
			border-bottom: 2px solid #ED6B86 !important;
		}
	}

	// document pdf and skills area
	aside div {
		padding-top: 0;
	}

	.document-pdf, .skills-link {
		font-size: 14px;
		color: black;

		&:hover {
			font-weight: bold;
			color: #1C7C54;
		}
	}

	a:hover {
		font-weight: bold;
	}
}

</style>
