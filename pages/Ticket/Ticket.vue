<template>
	<view>
	<image  class="OrderImage" src="../../static/icon/add_1.png"></image>
	<view class="Nothing">暂无订单~</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.OrderImage
	{
		height: 180rpx;
		width: 180rpx;
		margin-top:330rpx;
		margin-left: 300rpx;
	}
	.Nothing
	{
		margin-left: 42%;
		color: #D3D3D3;
		margin-top:15rpx;
		margin-left: 330rpx;
		font-size: 26rpx;
	}

</style>
