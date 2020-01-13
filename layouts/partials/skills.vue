<template lang="html">

	<section id="skills" class="row d-flex flex-wrap ">
		<div class="col-12">
			<h2> {{ title }} </h2>
		</div>

		<!-- ..................... front end skills ..................... -->
		<div v-for="frontend in frontend" id="skills-front" class="col-8 col-md-12 skill-card">
			<i :class=" frontend.icon "></i>
			<h3 class="text-center"> {{ frontend.category }} </h3>
			<div class="d-flex justify-content-center">
				<p v-for="items in frontend.items" class="text-center"> {{ items }} </p>
			</div>
		</div>

		<!-- ........ skills project mana / web analytics / digital mkt ........ -->
		<div v-for="skill in skills" class="col-8 col-md-4 skill-card">
			<i :class=" skill.icon "></i>
			<h3 class="text-center"> {{ skill.category }} </h3>
			<div class="d-flex justify-content-center">
				<p v-for="items in skill.items" class="text-center"> {{ items }} </p>
			</div>
		</div>
	</section>

</template>

<script>
export default {
	data() {
		return {
			title: 'Skills',
			frontend: [
				{
					category: 'frontend',
					icon: 'far fa-file-code',
					items:[
						'html',
						'css',
						'sass',
						'javascript',
						'jquery',
						'vue js',
						'webpack (vue-cli3)',
						'nuxt.js',
						'node js',
						'wordpress',
						'bootstrap',
						'materializecss',
						'responsive design',
						'git'
					]
				}
			],
			skills: [
				{
					category: 'project management tools',
					icon: 'fas fa-clipboard-check',
					items: [
						'github',
						'jira',
						'YouTrack',
						'Trello',
						'Slack',
						'Spark',
						'Google G Suite'
					]
				},
				{
					category: 'web analytics',
					icon:'fas fa-asterisk',
					items:[
						'google analytics',
						'eulerian'
					]
				},
				{
					category: 'digital channels',
					icon: 'fas fa-chart-line',
					items: [
						'SEO',
						'Management & optimization of web-marketing campaigns (affiliation, social media, search, emailing etc)'
					]
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


#skills {
	padding: 100px 0;
	background: #DDFFF7;
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	-ms-flex-wrap: wrap;
	    flex-wrap: wrap;
	-webkit-box-pack: center;
	    -ms-flex-pack: center;
	        justify-content: center;


	h2 {
		margin-bottom: 2em;
		text-align: center;
		letter-spacing: 3px;
		font-size: 3em;
	}

	.skill-card {
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
		-webkit-box-pack: start;
		    -ms-flex-pack: start;
		        justify-content: flex-start;

		h3 {
			letter-spacing: 2px;
		}

		div {
			padding: 2em 17px 5em;
			display: -webkit-box;
			display: -ms-flexbox;
			display: flex;
			-ms-flex-wrap: wrap;
			    flex-wrap: wrap;
			-webkit-box-pack: center;
			    -ms-flex-pack: center;
			        justify-content: center;
			width: 90%;
		}

		i {
			font-size: 30px;
			margin-bottom: 1em;
		}

	}

	.text-center {
		text-align: center;
	}

	p {
		letter-spacing: 0.5px;
		font-weight: 400;
		line-height: 2.5em;
		padding-right: 1em;
	}

}


</style>
