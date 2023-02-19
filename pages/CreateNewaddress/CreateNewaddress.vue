<template>
	<view class="AddressMsg">
		<view class="MsgDetails">
			<view class="MsgHeader">收件人</view>
			<textarea class="MsgText" placeholder="请输入收件人姓名"></textarea>
			<view class="MsgHeader">手机号</view>
			<textarea class="MsgText" placeholder="请输入手机号"></textarea>
			<view class="MsgHeader">地区</view>
			<textarea class="MsgText" placeholder="点击选择地区"></textarea>
			<view class="MsgHeader">详细地址</view>
			<textarea class="MsgText" placeholder="详细地址,楼牌号等"></textarea>
			<view class="MsgHeader"></view>
			<textarea class="MsgText" placeholder=""></textarea>
			
		</view>
		<view class="button">
			<button class="preserve">保存</button>
		</view>
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
	.AddressMsg {

		display: flex;
		flex-direction: column;
		background-color: #DCDCDC;

	}

	.MsgDetails {
		display: flex;
		flex-wrap: wrap;
		margin-top: 20rpx;
		justify-items: center;
		
	}

	.MsgHeader {
		margin-top: 2rpx;
		width: 150rpx;
		height: 70rpx;
		background-color: white;
		padding-top: 40rpx;
	
	}

	.MsgText {
		margin-top: 1rpx;
		height: 70rpx;
		background-color: white;
	padding-top: 40rpx;
		
	}
	.button
	{
		background: white;
	}
	.preserve
	{
		background-color: #FF7F00;
		margin-top: -5px;
		border-radius: 60rpx;
		border: #FF7F00;
		height: 80rpx;
		width:650rpx;
		color: white;
		margin-left: 28rpx;
		font-size: 32rpx;
	}
</style>
