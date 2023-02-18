<template>
	<view>
	<image class="post" src="../../static/icon/fly_1.png">
	<view class="no">您还没有发布出售信息哦~</view>
	<button class="gopost" size="mini">去发布</button>
		
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
.post
{
	height: 190rpx;
	width: 190rpx;
	margin-left: 285rpx;
	margin-top: 320rpx;
}
.no
{
	margin-left: 25%;
	margin-top: 2%;
	color: gray;
}
.gopost
{
	height: 70rpx;
	width: 205rpx;
	margin-left: 285rpx;
	margin-top: 50rpx;
	background-color:#EE7621;
	color: white;
	border-radius: 50rpx;
	font-size:30rpx;
}


</style>
