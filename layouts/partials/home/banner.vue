<template lang="">

	<section  class="row">

		<div class="wrapper">

			<div class="cover">
				<div class="titles">
					<h2> Claire J. </h2>
					<p> Front-end Developer </p>
				</div>

				<div class="cats">
					<a href="/portfolio"> Explore projects </a>
					<a href="/about"> View profile </a>
				</div>

			</div>
		</div>

	</section>

</template>

<script>

export default {
}
</script>

<style lang="scss">

// call to actions to page redirection
.cats {
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	-webkit-box-orient: horizontal !important;
	-webkit-box-direction: normal !important;
	    -ms-flex-direction: row !important;
	        flex-direction: row !important;
	-webkit-box-pack: center;
	    -ms-flex-pack: center;
	        justify-content: center;
	-webkit-box-align: center;
	    -ms-flex-align: center;
	        align-items: center;

	margin-top: 2em;

	width: 100%;

	a {
		padding: 0.5em 2em ;
		margin: auto 20px;
		border: 2px solid white;
		color: white;
		&:hover {
			color: #FAB3A9;
			border: 2px solid #ED6B86;
			background: rgba(0,0,0, 0.1);
		}
	}
}


.wrapper {
	background-position: bottom right;

	height: 100vh;
	width: 100vw;
	text-align: center;
	background: url(https://raw.githubusercontent.com/claire-jacquet/week-10-portfolio/master/images/parallax/main-8.jpg);

	display: -webkit-box;

	display: -ms-flexbox;

	display: flex;
	-webkit-box-orient: vertical;
	-webkit-box-direction: normal;
	    -ms-flex-direction: column;
	        flex-direction: column;
	-webkit-box-align: center !important;
	    -ms-flex-align: center !important;
	        align-items: center !important;
	-webkit-box-pack: center !important;
	    -ms-flex-pack: center !important;
	        justify-content: center !important;
}

.cover {
	height: 100%;
	width: 100%;
	z-index: 10;

	padding: 0;
	margin: 0;

	background-image: -webkit-gradient(linear, left bottom, right top, from(#d16ba5B3), color-stop(#c777b9B3), color-stop(#ba83caB3), color-stop(#aa8fd8B3), color-stop(#9a9ae1B3), color-stop(#8aa7ecB3), color-stop(#79b3f4B3), color-stop(#69bff8B3), color-stop(#52cffeB3), color-stop(#41dfffB3), color-stop(#46eefaB3), to(#5ffbf1B3));

	background-image: -o-linear-gradient(left bottom, #d16ba5B3, #c777b9B3, #ba83caB3, #aa8fd8B3, #9a9ae1B3, #8aa7ecB3, #79b3f4B3, #69bff8B3, #52cffeB3, #41dfffB3, #46eefaB3, #5ffbf1B3);

	background-image: linear-gradient(to right top, #d16ba5B3, #c777b9B3, #ba83caB3, #aa8fd8B3, #9a9ae1B3, #8aa7ecB3, #79b3f4B3, #69bff8B3, #52cffeB3, #41dfffB3, #46eefaB3, #5ffbf1B3);

	display: -webkit-box;

	display: -ms-flexbox;

	display: flex;
	-webkit-box-orient: vertical;
	-webkit-box-direction: normal;
	    -ms-flex-direction: column;
	        flex-direction: column;
	-webkit-box-align: center !important;
	    -ms-flex-align: center !important;
	        align-items: center !important;
	-webkit-box-pack: center !important;
	    -ms-flex-pack: center !important;
	        justify-content: center !important;

	.titles {
		display: -webkit-box;
		display: -ms-flexbox;
		display: flex;
		-webkit-box-orient: vertical;
		-webkit-box-direction: normal;
		    -ms-flex-direction: column;
		        flex-direction: column;
		-webkit-box-align: start;
		    -ms-flex-align: start;
		        align-items: flex-start;
		-ms-flex-pack: distribute;
		    justify-content: space-around;

		h2 {
			font-size: 6em;
			color: white;
			margin: 0 auto;
			padding: 0;
			text-transform: lowercase;
			text-shadow: 1px 1px  rgba(71, 71, 71, 0.8);

		}
		p {
			font-size: 3em;
			text-transform: lowercase;
			letter-spacing: 5px;
			color: white;
			margin: 0 auto;
			padding: 1em;
			text-shadow: 1px 1px  rgba(71, 71, 71, 0.8);
		}
	}

}

</style>
