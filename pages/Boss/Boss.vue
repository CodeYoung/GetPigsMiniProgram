<template>
	<view class="boss">
		<view class="Mainpage">
			<view class="line"></view>
			<view class="BossInfoName">
				<view class="Message">*姓名:</view>
				<textarea class="MsgText" placeholder="请输入真实姓名"></textarea>
			</view>
			<view class="Oneline"></view>
			<view class="BossInfoName">
				<view class="Message">*联系电话:</view>
				<textarea class="MsgText" placeholder="请输入联系电话"></textarea>
			</view>
			<view class="Oneline"></view>
			<view class="BossInfoName">
				<view class="Message">*上传身份证:</view>
				<view class="button"></view>
				
				<button class="zhengmian">
					<image class="zhengmianImg" src="../../static/icon/uploadImg.png"></image>
				</button>

				<button class="fanmian">
					<image class="zhengmianImg" src="../../static/icon/uploadImg.png"></image>
				</button>
			</view>
			<view class="word">身份证正面图片</view>
			<view class="beimian">身份证背面图片</view>
			
			<view class="Oneline" style="margin-top: 35rpx;"></view>
			
			<view class="Cnum" style="height: 120rpx;">
				<view class="Mess">*车牌号:</view>
				<textarea class="Msg" placeholder="请输入车牌号"></textarea>
			</view>
			<view class="Oneline" style="margin-top: 1px;"></view>
			<view class="button">
				<button class="preserve">确定申请</button>
			</view>
			
			
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
<style lang="scss">
	.boss {
		.Mainpage {

			display: flex;
			flex-direction: column;
			justify-items: center;

			.line {
				height: 17rpx;
				background-color: #DCDCDC;

			}

			.BossInfoName {
				// background-color: gray;

				display: flex;

				// flex-direction: column;
				.Message {
					background-color: white;
					margin-top: 30rpx;
					width: 220rpx;
					margin-left: 20rpx;
					// height: 100rpx;
					// background-color: white;
					padding-top: 6rpx
				}

				.MsgText {
					// background-color: white;
					// margin-top: 2rpx;
					height: 110rpx;
					// background-color: white;
					// padding-top: 20rpx;
					width: 80%;
					padding-left: 40rpx;
					line-height: 115rpx;
					font-size: 30rpx;


				}
			}

			.Oneline {
				background-color: #DCDCDC;
				margin: 0 3%;
				height: 3rpx;
			}

			.zhengmian {
				right: 120rpx;
				top: 110rpx;
				height: 100px;
				width: 150px;
				color: #DCDCDC;

				.zhengmianImg {
					height: 100px;
					width: 100px;
				}

			}

			.fanmian {
				right: 70rpx;
				top: 110rpx;
				height: 100px;
				width: 150px;
				color: #DCDCDC;

				.zhengmianImg {
					height: 100px;
					width: 100px;
				}

			}

			.butt {
				margin-top: 100rpx;
			}

			.Nline {
				background-color: #DCDCDC;

				height: 3rpx;
			}

			.Mess {
				margin-top: 30rpx;
				width: 220rpx;
				margin-left: 20rpx;
				padding-top: 6rpx
			}

			.Msg {
				padding-left: 130px;
				line-height: 115rpx;
				height: 110rpx;
				width: 80%;
				font-size: 30rpx;
				bottom: 40px;
			}
			.button{
				
			}
			.preserve{
				background-color: #FF7F00;
				margin-top: 98px;
				border-radius: 60rpx;
				border: #FF7F00;
				height: 80rpx;
				width: 700rpx;
				color: white;
				margin-left: 28rpx;
				font-size: 32rpx;
			}
		    .word{
				font-size: 1rpx;
				margin-left: 150rpx;
				display: flex;
				margin-top: 60px;
			}
			.beimian{
				font-size: 1rpx;
				margin-left: 240px;
				display: flex;
				margin-top: 280px;
				position: fixed;
			}

		}

	}
</style>
