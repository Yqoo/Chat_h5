<template>
	<view class="map">
		<web-view src="../../static/map.html"></web-view>
	</view>
</template>
<script>
	import qqmapsdk from '@/js_sdk/wxmp-qqmap/qqmap-wx-jssdk.js';
	export default {
		data() {
			return {};
		},
		onLoad() {
			const { windowHeight } = uni.getSystemInfoSync();
			this.height = windowHeight;
		},
		methods: {}
	}
</script>

<style lang="scss">
#container{
	/*地图(容器)显示大小*/
	width:1200px;
	height:400px;
}
</style>
