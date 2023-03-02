<template>
	<view class="mainPage">
		<view class="line"></view>
		<view class="inputBox">
			<view class="uni-form-item uni-column">
				<view style="color: red;">*</view>
				<view class="title">收购总金额:</view>
				<input class="uni-input" type="number" placeholder="请填写金额" />元
			</view>
			<view class="lineOne"></view>
			<view class="uni-form-item uni-column">
				<view style="color: red;">*</view>
				<view class="title">收购数量:</view>
				<input class="uni-input" type="number" placeholder="请填写数量" />头
			</view>
			<view class="lineOne"></view>
			<view class="uni-form-item uni-column">
				<view style="color: red;">*</view>
				<view class="title">收购总重量:</view>
				<input class="uni-input" type="number" placeholder="请填写重量" />
				斤
			</view>
			<view class="lineOne"></view>
			<view ><text style="color: red;">*</text>
				上传图片:
			</view>
		</view>
		<view class="BtnImage">
			<button size="mini">
				<image src="../../static/icon/uploadImg.png" class="ImgPicture"></image>
			</button>
		</view>
		<view style="color:#C0C0C0;font-size: 10rpx;margin: 40rpx;margin-left: 9px;">至少上传<text style="color:#FF8C00 ;">1</text>张，最多上传<text style="color:#FF8C00 ;">6</text>张</view>
		<view>
			
		</view>
		<view>
			<button class="BtnSure">
				确定
			</button>
		</view>

	</view>
</template>

<script>
</script>

<style lang="scss">
	.mainPage {
		// background-color: $uni-bg-color;

		.inputBox {
			// background-color: lightgrey;
			padding-top: 10px;
			margin-left: 10px;
			margin-right: 10px;

			.uni-form-item {
				height: 30px;
				margin-top: 3rpx;
				padding-top: 10px;

				// padding-left: 10px;
				// padding-right: 10px;
				background-color: $uni-bg-color;
				display: flex;

				.title {
					// text-align: center;
					width: 100px;
				}
				.uni-input{
					width: 470rpx;
				}
			}
		}

		.BtnImage {
			margin: 10rpx 20rpx;
			height: 150rpx;
			width: 150rpx;
		}

		.ImgPicture {
			height: 150rpx;
			width: 150rpx;
		}

		.BtnSure {
			margin-top: 220px;
			margin-left:20px;
			margin-right: 20px;
			border-radius: 60rpx;
			// padding:100rpx;
			background-color: #FF8C00;
		}

		.line {
			margin-top: 30rpx;
			background-color: $uni-bg-color-grey;
			height: 20rpx;
		}

		.lineOne {
			background-color: $uni-bg-color-grey;
			height: 5rpx;
			width: 94%;
			margin: 3%;
		}
	}
</style>
