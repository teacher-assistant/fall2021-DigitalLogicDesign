<template>
	<div>
		<div class="alert alert-dark">
			<h3 class="alert-head">
				News
			</h3>
			<div :class="getClass(index)" v-for="(news, index) in news_list">
				<div class="d-flex justify-content-between">
					<span>
						{{ news.body }}
					</span>
					<span>
						{{ news.date }}
					</span>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
export default {
	data(){
		return{
			classes:[
				'alert alert-info',
				'alert alert-primary',
				'alert alert-success',
				'alert alert-warning'
			],
			news_list:[]
		}
	},
	methods:{
		getClass(index){
			return this.classes[index%this.classes.length]
		}
	},
	mounted() {
	    this.$nextTick(()=>{
		  	this.$axios.$get('https://teacher-assistant.github.io/fall2021-DigitalLogicDesign/News.json')
	        .then(response=>this.news_list=response)
	    })
  	}
}
</script>