<template>
	<view class="ServicePage">
		<view class="firstPart">
			<image class="homeImg" src='../../static/other/组 276.png'></image>
		</view>
		<view class="secondPart">
			<image class="phoneImg" src="../../static/icon/phone.png"></image>
			<view class="phone">客服电话：{{Phone}}</view>
			<button class="call" size="mini">拨打</button>
		</view>
		<view class="secondPart">
			<image class="phoneImg" src="../../static/icon/phone.png"></image>
			<view class="phone">客服微信：{{WeChat}}</view>
			<button class="call" size="mini">复制</button>
		</view>
		<view class="ThirdPart">
			<image class="ImgQR" src="../../static/other/微信图片_20230226054046.jpg"></image>
			<view class="Tips" >保存二维码到手机，微信扫一扫添加客服微信</view>
			<button class="BtnSaveQR">保存二维码</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Phone: "023-81251562",
				WeChat: "jasdhl1726",
				qrShow:false,
			}
		},
		methods: {
			//**生成二维码**//
			qrFun(text) {
				this.qrShow = true
				uQRCode.make({
					canvasId: 'qrcode',
					componentInstance: this,
					text: text,
					size: 150,
					margin: 0,
					backgroundColor: '#ffffff',
					foregroundColor: '#000000',
					fileType: 'jpg',
					errorCorrectLevel: uQRCode.errorCorrectLevel.H,
					success: res => {}
				})
			}
		}
	}
</script>

<style lang="scss">
	.ServicePage {

		.firstPart {
			width: 100%;
			height: 50%;

			.homeImg {
				width: 100%;
				height: 600rpx;
			}
		}

		.secondPart {
			height: 20%;
			display: flex;
			flex-direction: row;
			margin-top: 50rpx;

			.phoneImg {
				padding-left: 80rpx;
				// background-color: gray;
				width: 50rpx;
				height: 50rpx;
			}

			.phone {
				// background-color: gray;
				margin-left: 20rpx;
			}

			.call {
				height: 50rpx;
				font-size: 30rpx;
				// padding-top: 1rpx;
				line-height: 40rpx;
				width: 100rpx;
				// text-align: center;
				margin-left: 40rpx;
				padding: 1rpx 0rpx;
				border-radius: 50rpx;
				border: 3rpx solid #00aaff;
				color: #00aaff;
				/* align-items: center; */
			}
		}
		.ThirdPart{
			.ImgQR{
				margin: 0 5%;
			}
			.Tips{
				text-align: center;
				font-size: 20rpx;
				color: $uni-text-color-grey;
			}
			.BtnSaveQR{
				margin: 20rpx 20%;
				border-radius: 60rpx;
				border: 2rpx solid $uni-text-color-grey;
				background-color: $uni-bg-color;
			}
		}
	}
</style>
