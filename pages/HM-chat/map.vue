<template>
	<view class="map">
		 <view class="page-section page-section-gap">
					<map style="width: 100%; height: 800px;"
						:latitude="latitude"
						:longitude="longitude"
						:markers="covers">
					</map>
			</view>
	</view>
</template>
<script>
	import qqmapsdk from '@/js_sdk/wxmp-qqmap/qqmap-wx-jssdk.js';
	export default {
		data() {
			return {
				height: Number,
				latitude: 39.909,
				longitude: 116.39742,
				covers: [{
							latitude: 39.909,
							longitude: 116.39743,
							iconPath: '@/static/face.jsp',
							title:'xxxxx'
					}]
			};
		},
		onLoad() {
			const { windowHeight } = uni.getSystemInfoSync();
			this.height = windowHeight;
			this.initMap()
		},
		methods: {
			initMap() {
				 const QQMapWX = new qqmapsdk({
							key: '54KBZ-372CF-QTEJS-N7YQU-GAOV5-GLFOT'
					});
					uni.getLocation({
						type:'gcj02',
						success: res => {
							console.log(res)
						}
					})
				//定义地图中心点坐标
			/* var map = new qq.maps.Map(document.getElementById(), {
					center: new qq.maps.LatLng(39.916527,116.397128),
					zoom:8,
					disableDefaultUI: true,
					zoom: 17.2,   //设置地图缩放级别
					pitch: 43.5,  //设置俯仰角
					rotation: 45 
				}); */
			}
		}
	}
</script>

<style lang="scss">
#container{
	/*地图(容器)显示大小*/
	width:1200px;
	height:400px;
}
</style>
