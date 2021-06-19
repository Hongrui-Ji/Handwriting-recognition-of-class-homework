<template>
	<view>
		<htz-signature @sumbit="sumbit"  @fail="fail" cid="ceshi1"></htz-signature>
	</view>
</template>

<script>
	import htzSignature from '@/components/htz-signature/htz-signature.vue'
	export default {
		data() {
			return {
			}
		},
		components: {
			htzSignature,
		},
		mounted() {
			this.$nextTick(function() {
			});

		},
		methods: {	
			sumbit(res){
				console.log('sumbit',res)
				try {
				    uni.setStorageSync('ceshiUrl', res.tempFilePath);
					uni.navigateBack();
				} catch (e) {
				    // error
				}
			},
			fail(err){
				console.log('fail',err)
			},
		}
	}
</script>

<style>

</style>
