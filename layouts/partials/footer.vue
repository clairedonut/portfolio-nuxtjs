<template lang="html">

	<footer class="container-fluid">
		<p> {{ title }} </p>
		<div class="">
			<a v-for="footer in footers" :href="footer.link">
				<i v-bind:class=" footer.icon "></i>
			</a>
		</div>
	</footer>

</template>

<script>
export default {
	data() {
		return {
			title: 'Claire | Front-end developper',
			footers: [
				{
					name: 'email',
					icon: 'fas fa-at fa-sm',
					link: 'claire.j.jacquet@gmail.com'
				},
				{
					name: 'linkedin',
					icon: 'fab fa-linkedin-in fa-sm',
					link: 'https://www.linkedin.com/in/clairejacquet'
				},
				{
					name: 'github',
					icon: 'fab fa-github fa-sm',
					link: 'https://github.com/clairedonut'
				}
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

footer {
    position: fixed !important;
    width: 100%;
    bottom: 0;
    left: 0;
    z-index: 100;

	@include flex-row(space-between,flex-end);
	padding: 0.5em  3em;
    background-color: #76EEC6;

	p {
		color:#19323C;
		font-weight: 200;
		margin: 0;
	}
	div {
		@include flex-row(flex-end,flex-end);
	}
	a {
		color:#19323C;
		margin: 0 0.8em ;
		font-weight: 200;
		&:hover {
			color: #ED6B86;
			text-decoration: none;
		}
	}
}
</style>
