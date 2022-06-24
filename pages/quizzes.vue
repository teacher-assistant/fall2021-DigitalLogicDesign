<template>
	<div class="container d-grid gap-2">
    	<div></div>
		<MainCard title="Quizzes Status" />
		<QuizzestatusTable />
	</div>
</template>

<script>
import 'boxicons'
export default {
	head(){
  		return{
  			title:'Quizzes Status'
  		}
  	}
}
</script>
