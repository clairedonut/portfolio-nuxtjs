<template lang="html">

	<div id="slider">

		<!-- ...... slider arrow left ...... -->

		<div class="arrow left" @click="prev" >
			<i class="fas fa-chevron-left"></i>
		</div>

		<!-- ...... slider image ...... -->

		<div v-for="number in [currentNumber]" transition="fade" class="images">
			<img v-if=" $route.params.id == gallery.id" v-for="gallery in gallery" :src="gallery.images[Math.abs(currentNumber) % gallery.images.length]"/>
		</div>

		<!-- <div v-for="number in [currentNumber]" transition="fade" class="images">
			<img v-if=" $route.params.id == gallery.id" v-for="gallery in gallery" :src="gallery.images[Math.abs(currentNumber) % 2]"/>
		</div> -->


		<!-- ...... slider arrow right ...... -->

		<div class="arrow right" @click="next" >
			<i class="fas fa-chevron-right"></i>
		</div>

	</div>

</template>

<script>
export default {
	data() {
		return {
			gallery: [
				{
					id: 'dentist',
					images: [
						'/img/dentist-1.png',
						'/img/dentist-2.png',
						'/img/dentist-5.png',
						'/img/dentist-6.png',
						'/img/dentist-7.png',
						'/img/dentist-8.png',
						'/img/dentist-9.png',
						'/img/dentist-10.png',
						'/img/dentist-11.png',
						'/img/dentist-12.png'
					]
				},
				{
					id: 'bobuncafe',
					images: [
						'/img/bobuncafe-1.png',
						'/img/bobuncafe-2.png',
						'/img/bobuncafe-3.png',
						'/img/bobuncafe-4.png',
					]
				},
				{
					id: 'airbnb',
					images: [
						'/img/airbnb-1.png',
						'/img/airbnb-anim.gif',
						'/img/airbnb-desktop.png',
						'/img/airbnb-tablette.png'
					]
				},
				{
					id: 'frenchstranding',
					images: [
						'/img/frenchstranding-md.png',
						'/img/frenchstranding-1.png',
						'/img/frenchstranding-2.png'
					]
				},
				{
					id: 'kawaii-icecream',
					images: [
						'/img/kawaiiicecream-1.png',
						'/img/kawaiiicecream.png'
					]
				},
				{
					id: 'strategies-obliques',
					images: [
						'/img/strategiesobliques-anim.gif',
						'/img/strategiesobliques.png',
						'/img/strategiesobliques-3.png',
						'/img/strategiesobliques-1.png',
						'/img/strategiesobliques-2.png',
						'/img/strategiesobliques-4.png',
						'/img/strategiesobliques-5.png',
						'/img/strategiesobliques-6.png',
						'/img/strategiesobliques-7.png',
						'/img/strategiesobliques-8.png',
					]
				},
				{
					id: 'posters',
					images: [
						'/img/posters-1.png',
						'/img/posters-5.png',
						'/img/posters-2.png',
						'/img/posters-3.png',
						'/img/posters-4.png',
						'/img/posters-anim.gif'
					]
				},
				{
					id: 'teesandtigers',
					images: [
						'/img/teesandtigers-1.png',
						'/img/teesandtigers-anim.gif',
						'/img/teesandtigers.png',
						'/img/teesandtigers-2.png',
						'/img/teesandtigers-3.png'
					]
				},
				{
					id: 'teesandtigers-nl',
					images: [
						'/img/teestiger-nl.png',
						'/img/teestiger-nl-1.png',
						'/img/teestiger-nl-2.png',
						'/img/teestiger-nl-3.png'
					]
				},
				{
					id: 'wordpress',
					images: [
						'/img/wp-blog-1.png',
						'/img/wp-2.png',
						'/img/wp-3.png'
					]
				},
				{
					id: 'portfolio-nuxt',
					images: [
						'/img/portfolio-1.png',
						'/img/portfolio.png',
						'/img/portfolio-2.png',
						'/img/portfolio-3.png',
						'/img/portfolio-4.png'
					]
				}
			],
			images: ['http://i.imgur.com/vYdoAKu.jpg', 'http://i.imgur.com/PUD9HQL.jpg', 'http://i.imgur.com/Lfv18Sb.jpg', 'http://i.imgur.com/tmVJtna.jpg', 'http://i.imgur.com/ZfFAkWZ.jpg'],
			currentNumber: 0,
			timer: null
		}
	},
	ready: function () {
		this.startRotation();
	},

	methods: {

		next: function() {
			this.currentNumber += 1
		},

		prev: function() {
			this.currentNumber -= 1
		}
	}
}
</script>

<style lang="scss">

/* ******* slider images transitions ******* */

.fade-transition {
	-webkit-transition: all 0.8s ease;
	-o-transition: all 0.8s ease;
	transition: all 0.8s ease;
	overflow: hidden;
	visibility: visible;
	opacity: 1;
	position: absolute;
}
.fade-enter, .fade-leave {
	opacity: 0;
	visibility: hidden;
}

#slider {
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	-webkit-box-orient: horizontal;
	-webkit-box-direction: normal;
	    -ms-flex-direction: row;
	        flex-direction: row;
	-ms-flex-pack: distribute;
	    justify-content: space-around;
	-webkit-box-align: center;
	    -ms-flex-align: center;
	        align-items: center;

	i {
		color: rgba(0,0,0,.11);
		&:active {
			color: black;
			text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
		}
	}
	&:hover {
		i {
			color: #373E40;
		}
	}

	.images {
		margin: 0;
		padding: 0;
	}

	.arrow {
		text-align: center;
		z-index: 1000;
		cursor: pointer;

		width: 60px;
		height: 100%;

		display: -webkit-box;

		display: -ms-flexbox;

		display: flex;
		-webkit-box-align: center;
		    -ms-flex-align: center;
		        align-items: center;
		-webkit-box-pack: center;
		    -ms-flex-pack: center;
		        justify-content: center;

		position: absolute;
	}

	i {
		font-size: 30px;
		z-index: 30;
	}

	.images {
		z-index: 0;
		width: 100%;

		overflow: hidden;
		max-height: 500px;

		display: -webkit-box;

		display: -ms-flexbox;

		display: flex;
		-webkit-box-align: start;
		    -ms-flex-align: start;
		        align-items: flex-start;
		-webkit-box-pack: center;
		    -ms-flex-pack: center;
		        justify-content: center;
	}

}

#site .images img {
	height: auto !important;
	width: 100% !important;
}

/* ******* slider arrows  ******* */

.left {
	left: 5%;
}

.right {
	right: 5%;
}
</style>
