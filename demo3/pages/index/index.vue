<template>
	<view>

		<button type="primary" @click="goto" style="margin: 20rpx;">打开手写板</button>
		<view style="margin:30rpx 20rpx 20rpx;font-size: 36rpx;">结果 ：</view>
		<image :src="resultUrl" style="width: 100%;" mode="widthFix"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				resultUrl: '',
			}
		},
		mounted() {
			this.$nextTick(function() {});
		},
		onShow() {
			try {
				if (uni.getStorageSync('ceshiUrl')) {
					this.resultUrl = uni.getStorageSync('ceshiUrl');
					uni.removeStorageSync('ceshiUrl');
				}

			} catch (e) {
				// error
			}
		},
		methods: {
			goto() {
				uni.navigateTo({
					url: '../signature/signature'
				});
			}
		}
	}
</script>

<style>

</style>
