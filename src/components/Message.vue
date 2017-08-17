<template>
	<article class="message" v-show="isVisible">
		<div class="message-header">
			<p>{{title.split('').reverse().join('')}}</p>
			<button class="delete" aria-label="delete" @click="isVisible = false" ></button>
		</div>
		<div class="message-body">
			{{body}}
			<p>{{reversedMessage}}</p>
		</div>
	</article>
</template>


<script type="text/javascript">
	export default{
		props: ['title', 'body'],
		data(){
			return { 
				message: '12345',
				isVisible: true
			};
		},

		computed: {
			reversedMessage(){
				return this.message.split('').reverse().join('');
			}
		},

		methods: {
			hideModal(){
				this.isVisible = false;
			}
		}
	}
</script>


<style type="text/css">
	

</style>