<template>
	<div>
		<h2>The Count Is:{{ count }}</h2>
		<p>
			<a class="button" @click="count +=20">increment</a>
		</p>


	</div>
</template>


<script>
	export default{
		data(){
			return { count: 0 };
		}
	}


</script>


<style>
	



</style>