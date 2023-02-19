<template>
	<view>
	<image class="Pig" src="../../static/login/loginMain.png">
	<view class="apply">申请获得以下权限</view>
	<view class="aquire">获得你的公开信息(昵称、头像等)</view>
	<button class="Login">授权登录</button>
	<button class="cancel">取消</button>
	
	
	
		
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
.Pig
{
	height: 320rpx;
	width: 325rpx;
	margin-left: 200rpx;
	margin-top: 20%;
}
.apply
{
	margin-left: 4%;
	margin-bottom:2%;
	margin-top: 10%;
	font: size 30rpx;
	
}
.aquire
{
	margin-left: 4%;
	color: gray;
	margin-bottom: 5%;
	font-size:20rpx;
}
.Login
{
	height: 80rpx;
	width: 650rpx;
	margin-left: 40rpx;
	margin-top: 60rpx;
	font-size:30rpx;
	border-radius: 50rpx;
	background-color: #FF7F00;
	color: white;
}
.cancel
{
	height:80rpx;
	width: 650rpx;
	margin-left: 40rpx;
	margin-top: 40rpx;
	border-radius: 50rpx;
	font-size:30rpx;
	border: 0.1px solid #696969
}
</style>
