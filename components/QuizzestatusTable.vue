<template>
    <div class="alert alert-dark">
    	<h3>
    		Below table is updated <span class="alert-link">a few days after deadlines</span>
    	</h3>
    	<div class="table-responsive">
		<table class="table table-primary table-striped">
		  <thead>
		    <tr>
		      <th scope="col">#</th>
		      <th scope="col">Student Number</th>
		      <th scope="col">Quiz1</th>
		      <th scope="col">Quiz2</th>
		      <th scope="col">Quiz3</th>
		    </tr>
		  </thead>
		  <tbody>
		    <tr v-for="(student, index) in students">
		      <th scope="row">{{ index+1 }}</th>
		      <td>{{ student.id }}</td> 
		      <td> {{ student.Quiz1 }}</td>
		      <td> {{ student.Quiz2 }}</td>
		      <td> {{ student.Quiz3 }}</td>
		    </tr>
		  </tbody>
		</table>
    	</div>
    </div>
</template>

<script>
export default {
	data(){
		return{
			students:[]
		}
	},
  	mounted() {
	    this.$nextTick(()=>{
		  	this.$axios.$get('https://teacher-assistant.github.io/fall2021-DigitalLogicDesign/Quizzes.json')
	        .then(response=>this.students=response)
	    })
  	}
}
</script>