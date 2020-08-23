<template>
	<view>
		<map :style="{
				width: '100%',
				height: height + 'px'
			}" 
			:latitude="latitude"
			:longitude="longitude"
			:markers="covers"
			@markertap="markertap"
			@controltap="controltap"
			show-location
			:title="title">
		</map>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				id:0, // 使用 marker点击事件 需要填写id
				title: 'map',
				latitude: 39.909,
				longitude: 116.39742,
				covers: [{
					latitude: 39.909,
					longitude: 116.39742
				}, {
					latitude: 39.90,
					longitude: 116.39
				}],
				height: Number
			};
		},
		onLoad() {
			const { windowHeight } = uni.getSystemInfoSync();
			this.height = windowHeight;
		},
		methods: {
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

</style>
