<template>
	<view class="thispage">
		<view class="main">
			<image class="mainImg" src="../../static/other/组 277.png"></image>
		</view>
		<view class="blank">
			<image class="blankImg" src="../../static/common/reduce.png"></image>
			<button class="baocun">保存二维码</button>
			<view class="yangzhi">养殖交流群：jasdhl1726</view>


		</view>
		<view class="copyBtn">
			<button class="fuzhi">复制</button>
		</view>
		<view class="zi">扫码加群</view>
		<view class="zhongwen">保存二维码至手机，微信扫一扫加群</view>


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

<style lang="scss">
	.main {
		bottom: 200px;
		width: 100%;
		height: 100%;

		.mainImg {
			
		    height: 623px;
			width: 100%;
		}

		/* height: 1500rpx;
	width: 800rpx; */

	}

	.blank {
		position: fixed;
		bottom: 200px;
		margin-left: 30px;
		width: 170px;
		height: 250px;

		.blankImg {
			width: 280px;
			margin-left: 16px;
			bottom: 55px;
			height: 310px;
		}

		.baocun {
			left: 110rpx;
			bottom: 270rpx;
			border-radius: 40rpx;
			height: 80rpx;
			width: 400rpx;
			font-size: 15px;
			border: 0.5px solid #828282;
		}

		.yangzhi {
			position: fixed;
			top: 190rpx;
			left: 40px;
			font-size: 40rpx;
			color: white;
		}

		
	}
.copyBtn{
	
	
	.fuzhi {
		left: 550rpx;
		bottom: 550px;
		border-radius: 40rpx;
		height: 40rpx;
		width: 80rpx;
		font-size: 10rpx;
		padding-left: 1rpx;
		padding-right: 1rpx;
		background-color: transparent;
		border: 3rpx solid #F8F8FF;
		color: #F8F8FF;
		text-align: center;
		vertical-align: middle;
		line-height: 17px;
		position: fixed;
	}
}
	.zi {
		position: fixed;
		top: 360rpx;
		// padding-top: 150rpx;
		left: 300rpx;
		font-size: 26rpx
	}

	.zhongwen {
		position: fixed;
		top: 360px;
		left: 174rpx;
		color: gray;
		font-size: 1px;


	}
</style>
