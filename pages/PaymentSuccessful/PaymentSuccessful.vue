<template>
	<view>
	<image class="right" src="../../static/common/right.png">
	<view class="success">您已支付成功！</view>
	<button class="look">查看订单</button>
	<button class="return">返回首页</button>
		
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
.right
{
	height: 130rpx;
	width: 130rpx;
	margin-top: 230rpx;
	margin-left:305rpx;
}
.success
{
	margin-left: 35%;
	margin-top: 3%;
}
.look
{
	height: 60rpx;
	width: 190rpx;
	margin-left: 170rpx;
	margin-top: 120rpx;
	border-radius: 50rpx;
	font-size:5rpx;
	border: 0.1px solid #696969
	
}
.return
{
	height: 60rpx;
	width:190rpx;
	margin-right: 170rpx;
	margin-top: -60rpx;
	background-color: #FF7F00;
	color: white;
	border-radius: 60rpx;
	font-size:5rpx;
}

</style>
