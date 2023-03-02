<template>
	<view class="thispage">
		<view class="AddressMsg" v-show="!IsNoAdress">
			<view class="OrderLxrInfo">
				<view>
					<view class="OrderLxr">何先生 152****4567</view>
					<view class="OrderLxdz">重庆是南岸区台东路华侨中学东北侧约60米东路华上侨2栋17-3</view>
				</view>
				<button class="BtnSelectAdress">
					<image class="ImgSelectAdress" src="../../static/icon/Next.png"></image>
				</button>
			</view>
		</view>
		<view class="line" v-show="IsNoAdress"></view>
		<view class="AddAddress" v-show="IsNoAdress">
			<button class="BtnAddAddress">+ 新建地址</button>
		</view>
		<view class="OrderGoodsInfo">
			<image class="OrderGoodsImg" src="../../static/other/蒙版组 9.png"></image>
			<view class="OrderGoodsInfo">
				<view>复合维生素兽用注射液猪牛羊用产后消炎</view>
				<view class="OrderGoodsSellInfo">
					<view>{{money}}</view>
					<view class="OrderGoodsSellCount">
						<button class="btnCount" size="mini">-</button>
						<view style="text-align: center; padding-top: 10rpx; margin:0 10rpx;">{{count}}</view>
						<button class="btnCount" size="mini">+</button>
					</view>
				</view>
			</view>
		</view>

		<view class="line"></view>
		<view class="OrderMsg">
			<view class="ExpressHeader">运费</view>
			<view class="ExpressMoneyText">{{money}}</view>
		</view>
		<view class="lineOne"></view>
		<view class="OrderMsg">
			<view class="ExpressHeader">备注</view>
			<textarea class="ExpressText" placeholder="选填,备注内容~">{{money}}</textarea>
		</view>
		<view class="lineOne"></view>
		<view class="lineOne" v-show="!IsNoAdress" style="margin-top: 350rpx;"></view>

		<view class="OrderMsg" v-show="!IsNoAdress">
			<view class="TotalCountText">共 {{count}} 件商品 合计：</view>
			<view class="TotalMoneyText" style="color: red;font-weight: bold;">{{money}}</view>
			<button class="BtnPay" size="mini">确认支付</button>
		</view>
		<view class="OrderMsgNoAddress" v-show="IsNoAdress">
			<view class="TotalCountText">共 {{count}} 件商品 合计：</view>
			<view class="TotalMoneyText" style="color: red;font-weight: bold;">{{money}}</view>		
		</view>
		<button class="BtnNoAddressPay" v-show="IsNoAdress">确认支付</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				count: 1,
				money: '￥25.8',
				IsNoAdress: true
			}
		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.thispage {
		.AddressMsg {
			background-color: white;

			.OrderLxrInfo {
				background-color: $uni-bg-color-grey;
				margin: 30rpx;
				border-radius: 20rpx;
				padding-left: 30rpx;
				padding-top: 30rpx;
				padding-bottom: 30rpx;
				display: flex;

				.OrderLxr {
					font-weight: bold;
				}

				.OrderLxdz {
					padding-top: 10rpx;
					color: $uni-text-color-disable;
				}

				.BtnSelectAdress {
					border: none;
					line-height: 120rpx;
					text-align: center;
					width: 20rpx;

					.ImgSelectAdress {
						height: 15%;
						width: 10rpx;
						padding-top: 40rpx;
					}

					// background-image: ;
				}

				.BtnSelectAdress::after {
					border: none;
				}
			}
		}

		.AddAddress {

			margin: 30rpx;

			.BtnAddAddress {
				height: 200rpx;
				line-height: 200rpx;

				&::after {
					border: none;
				}
			}
		}

		.OrderGoodsInfo {
			display: flex;

			.OrderGoodsImg {
				margin: 20rpx;
				height: 180rpx;
				width: 180rpx;
			}

			.OrderGoodsInfo {
				display: flex;
				flex-direction: column;
				font-weight: bold;

				.OrderGoodsSellInfo {
					display: flex;
					margin-top: 70rpx;

					.OrderGoodsSellCount {
						display: flex;
						padding-left: 230rpx;

						.btnCount {
							height: 60rpx;
							width: 60rpx;
							padding-left: 25rpx;
							color: white;
							background-color: $uni-color-selected;
						}

						// .btnCount::after{
						// 	// background-color: $uni-color-selected;
						// 	color: white;
						// }
					}
				}
			}
		}

		.OrderMsg {
			display: flex;
			margin: 30rpx;

			.ExpressMoneyText {
				width: 90%;
				text-align: right;
			}

			.ExpressText {
				padding-left: 20rpx;
				width: 80%;
				height: 60rpx;
			}

			.BtnPay {
				margin-top: -20rpx;
				height: 70rpx;
				line-height: 70rpx;
				margin-left: 100rpx;
				background-color: $uni-color-selected;
				color: $uni-text-color-inverse;
			}
		}

		.OrderMsgNoAddress {
			display: flex;
			margin: 30rpx;

			.ExpressMoneyText {
				width: 90%;
				text-align: right;
			}

			.ExpressText {
				padding-left: 20rpx;
				width: 80%;
				height: 60rpx;
			}

			
		}
		.BtnNoAddressPay {
				// margin-top: -20rpx;
				height: 80rpx;
				line-height: 80rpx;
				margin-top: 250rpx;
				margin-left: 5%;
				width: 90%;
				background-color: $uni-color-selected;
				color: $uni-text-color-inverse;
				border-radius: 60rpx;
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
