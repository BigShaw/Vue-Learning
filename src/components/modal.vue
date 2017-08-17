<template>
	<div class="modal is-active">
		<div class="modal-background" @click="$emit('close')"></div>
		<div class="modal-content">
			<div class="box">
				<slot name="header"></slot>
				<slot><p>Defualt Text</p></slot>
			</div>
		</div>
		<button class="modal-close is-large" aria-label="close"></button>
	</div>


</template>

<script>
	export default{
		data(){
			return { 

			};
		},

		methods: {

		}
	}


</script>