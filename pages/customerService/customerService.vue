<template>
	<view class="ServicePage">
		<view class="firstPart">
			<image class="homeImg" src="../../static/icon/home.png"></image>
		</view>		
		<view class="secondPart">
			<image class="phoneImg" src="../../static/icon/phone.png"></image>
			<view class="phone">客服电话：023-81251562</view>
			<button class="call">拨打</button>
		</view>
	</view>
</template>

<script>
</script>

<style>
	.ServicePage
	{
		background-color: gray;
	}
/* 	.homeImg
	{
		width: 100rpx;
		height: 100rpx;
	} */
	.phoneImg
	{
		width: 50rpx;
		height: 50rpx;
	}
	.firstPart
	{
		width: 50%;
		height: 50%;		
	}
	.secondPart
	{
		background-color: gray;
		height: 20%;
		display: flex;
		flex-direction: row;
	}
	.phone
	{
		margin-left: 150rpx;
	}
	.call
	{
		height: 60rpx;
		font-size: 30rpx;
		padding-top: -0rpx;
		/* align-items: center; */
	}
</style>