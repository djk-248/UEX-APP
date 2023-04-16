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
				address: appConfig.UEX_Address,
				webviewStyles:{
					height: '95%'
				}
			}
		},
		onLoad() {
			// uni.setNavigationBarTitle({
			// 	title: appConfig.appName
			// })
				let height = 0; //定义动态的高度变量
				let statusbar = 0; // 动态状态栏高度
				uni.getSystemInfo({ // 获取当前设备的具体信息
					success: (sysinfo) => {
						statusbar = sysinfo.statusBarHeight;
						height = sysinfo.windowHeight;
					}
				});
				let currentWebview = this.$scope.$getAppWebview(); //获取当前web-view
				setTimeout(function() {
					var wv = currentWebview.children()[0];
					wv.setStyle({ //设置web-view距离顶部的距离以及自己的高度，单位为px
						top: statusbar, //此处是距离顶部的高度，应该是你页面的头部
						height: height-statusbar, //webview的高度
					})
				}, 200); //如页面初始化调用需要写延迟
			

		},
		methods: {
			
		}
	}
</script>

<style>

</style>