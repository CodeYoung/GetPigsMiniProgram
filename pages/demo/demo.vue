<template>
	<view class="boss">
		<view class="Mainpage">
			<view class="line"></view>
			<view class="BossInfoName">
				<view class="Message">姓名:</view>
				<textarea class="MsgText" placeholder="请输入真实姓名"></textarea>
			</view>
			<view class="Oneline"></view>
			<view class="BossInfoName">
				<view class="Message">*联系电话:</view>
				<textarea class="MsgText" placeholder="请输入联系电话"></textarea>
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

		// background-color: #ff0000;


		.Mainpage {
			// background-color: gray;

			display: flex;
			flex-direction: column;
			justify-items: center;

			.line {
				height: 17rpx;
				// background-color: #DCDCDC;
				background-color: #ff0000;
			}

			.BossInfoName {
				// background-color: gray;

				display: flex;

				// flex-direction: column;
				.Message {
					background-color: white;
					margin-top: 2rpx;
					width: 100rpx;
					// height: 100rpx;
					// background-color: white;
					padding-top: 2rpx
				}

				.MsgText {
					// background-color: white;
					// margin-top: 2rpx;
					height: 60rpx;
					// background-color: white;
					// padding-top: 20rpx;
					width: 80%;
					padding-left: 20rpx;

				}
			}

			.Oneline {
				background-color: gray;
				// color: black;
				height: 3rpx;
			}


		}
	}
</style>
