<script>
	import appConfig from '@/config/appConfig.js'
	import updaterMixins from '@/mixins/updater_mixins.js'
	export default {
		mixins: [updaterMixins],
		onLaunch: function() {
			console.log('App Launch')
			this.checkVersionUpdate()
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
</style>
