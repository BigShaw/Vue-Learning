<template>
	<input placeholder="Enter your coupon code." @blur="onCouponApplied">
</template>


<script>
	export default{
		data(){
			return {

			};
		},
		methods: {
			onCouponApplied(){
				Event.$emit('applied')
			}
		}
	}


</script>

