<template>
	<view class="page">
		<web-view :src="address"></web-view>
	</view>
</template>

<script>
	import appConfig from '@/config/appConfig.js'
	export default {
		data() {
			return {
				address: appConfig.UEX_Address
			}
		},
		onLoad() {
			uni.setNavigationBarTitle({
				title: appConfig.appName
			})
		},
		methods: {

		}
	}
</script>

<style>

</style>