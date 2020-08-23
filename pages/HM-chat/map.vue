<template>
	<view id="container" :style="{
		width: '100%',
		height: height + 'px'
	}">
		
	</view>
</template>
<script>
	export default {
		data() {
			return {
				height: Number
			};
		},
		onLoad() {
			const { windowHeight } = uni.getSystemInfoSync();
			this.height = windowHeight;
			this.initMap()
		},
		methods: {
			initMap() {
				//定义地图中心点坐标
				console.log(document.getElementById("container"))
				var map = new qq.maps.Map(document.getElementById("container"), {
					center: new qq.maps.LatLng(39.916527,116.397128),
					zoom:8,
					disableDefaultUI: true,
					zoom: 17.2,   //设置地图缩放级别
					pitch: 43.5,  //设置俯仰角
					rotation: 45 
				});
			},
			markertap(e) {
				console.log(e)
			},
			controltap(e) {
				console.log(e)
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
