<template>
	<view class="thispage">
		<view class="line"></view>
		<view class="WaitOutGoodsBox" v-show="ShowWaitOutGoodsBox">
			<view class="WaitOutGoodsImg">
				<image  src="../../static/icon/package_1.png"></image>
			</view>
			<view class="WaitOutGoodsText">
				待发货中，请耐心等待...
			</view>
		</view>
		<view class="CountDownBox" v-show="ShowCountDownBox">
			<view class="CountDownImg">
				<image  src="../../static/icon/clock.png"></image>
			</view>
			<view class="timeBox">
				<view>剩余</view>
				<view class="CountDown">{{countDown}}</view>
				<view>自动关闭</view>
			</view>
		</view>
		<view class="ExpressBox" v-show="ShowExpressBox">
			<view class="ExpressInfo">
				<view>物流信息</view>
				<view class="ExpressText">{{ExpressInfo.expressText}}</view>
			</view>
			<view class="ExpressDetail">
				<button class="BtnExpressDetail" size="mini">查看物流</button>
			</view>
		</view>
		<view class="AddressMsg">
			<view class="OrderLxrInfo">
				<view class="OrderLxr">何先生 152****4567</view>
				<view class="OrderLxdz">重庆是南岸区台东路华侨中学东北侧约60米东路华上侨2栋17-3</view>
			</view>
		</view>
		<view class="OrderGoodsInfo">
			<image class="OrderGoodsImg" src="../../static/other/蒙版组 9.png"></image>
			<view class="OrderGoodsInfo">
				<view>复合维生素兽用注射液猪牛羊用产后消炎</view>
				<view class="OrderGoodsSellInfo">
					<view>￥25.8</view>
					<view class="OrderGoodsSellCount">X3</view>
				</view>
			</view>
		</view>
		<view class="lineOne"></view>
		<view class="OrderPayInfo">
			<view>共计</view>
			<view class="goodsCount">1</view>
			<view>件商品 合计待付款：</view>
			<view class="goodsTotalPrice">￥25.8</view>
		</view>
		<view class="lineOne"></view>
		<view class="OrderDetailsInfo" v-for="item in OrderDetailsInfos">
			<view class="DetailsHeader">{{item.title}}</view>
			<view class="DetailsText">{{item.text}}</view>
			<!-- <view class="DetailsHeader">订单编号</view>
			<view class="DetailsText">1984981654987</view>
			<view class="DetailsHeader">下单时间</view>
			<view class="DetailsText">2022.08.08 12:00:00</view>
			<view class="DetailsHeader">订单备注</view>
			<view class="DetailsText">无</view> -->
		</view>
		<view class="BtnConfirm" v-show="ShowCountDownBox">
			<button class="BtnCancelOrder" size="mini">取消订单</button>
			<button class="BtnPayOrder" size="mini">去支付</button>
		</view>
		<view class="ConfirmGetGoods" v-show="ShowExpressBox">
			<button class="BtnConfirmGetGoods" >确定收货</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				countDown:"00 天 01 时 20 分 20 秒",
				OrderDetailsInfos:[{
					title:'订单状态',
					text:'待支付'
				},
				{
					title:'订单编号',
					text:'1984981654987'
				},
				{
					title:'下单时间',
					text:'2022.08.08 12:00:00'
				},
				{
					title:'订单备注',
					text:'无'
				}
				],
				ShowCountDownBox:false,
				ShowExpressBox:false,
				ShowWaitOutGoodsBox:true,
				ExpressInfo:{
					expressNum:"1",
					expressText:"您的包裹已配送至XXXX,请注意查收"
				}
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.thispage{
		// background-color: $uni-bg-color-grey;
		.WaitOutGoodsBox{
			.WaitOutGoodsImg{
				padding-top: 50rpx;
				// height: 100%;
				width: 100%;
				height: 80rpx;
				background-color: white;
				text-align: center;
				image{
					height: 100%;
					width: 80rpx;
				}
			}
			.WaitOutGoodsText{
				margin-left: 200rpx;
				padding-top: 10rpx;
				color: $uni-color-selected;
				font-size: 30rpx;
			}
			
		}
		.CountDownBox{
			background-color: $uni-bg-color-grey;
			.CountDownImg{
				padding-top: 50rpx;
				// height: 100%;
				width: 100%;
				height: 80rpx;
				background-color: white;
				text-align: center;
				image{
					height: 100%;
					width: 80rpx;
				}
			}
			.timeBox{
				display: flex;
				padding-left: 100rpx;
				background-color: white;
				.CountDown{
					color: $uni-color-selected;
				}
			}
		}
		.ExpressBox{
			border: 3rpx solid darkgray;
			width: 85%;
			margin: 8% 5%;
			padding: 20rpx;
			border-radius: 20rpx;
			display: flex;
			.ExpressInfo{
				.ExpressText{
					padding-top: 10rpx;
					color: $uni-text-color-disable;
				}
			}
			.ExpressDetail{
				text-align: center;
				padding: 20rpx;
				.BtnExpressDetail{
					padding: 2rpx;
					width: 150rpx;
					border-radius: 50rpx;
					border: 3rpx solid darkgray;
				}
			}
		}
		.AddressMsg{
			background-color: white;
			.OrderLxrInfo{
				background-color: $uni-bg-color-grey;
				margin: 30rpx;
				border-radius: 20rpx;
				padding: 30rpx;
				.OrderLxr{
					font-weight: bold;
				}
				.OrderLxdz{
					padding-top: 10rpx;
					color: $uni-text-color-disable;
				}
			}
		}
		.OrderGoodsInfo{
			display: flex;
			.OrderGoodsImg{
				margin: 20rpx;
				height: 180rpx;
				width: 180rpx;
			}
			.OrderGoodsInfo{
				display: flex;
				flex-direction: column;
				font-weight: bold;
				.OrderGoodsSellInfo{
					display: flex;
					margin-top: 80rpx;
					.OrderGoodsSellCount{
				
						padding-left: 370rpx;
					}
				}
			}
		}
		.OrderPayInfo{
			display: flex;
			padding-left: 220rpx;
			.goodsCount{
				color: $uni-color-selected;
				padding: 0 10rpx;
				
			}
			.goodsTotalPrice{
				color: red;
				font-weight: bold;
			}
		}
		.OrderDetailsInfo{
			display: flex;
			margin: 20rpx 0;
			.DetailsHeader{
				padding-left: 20rpx;
				color: $uni-text-color-grey;
			}
			.DetailsText{
				padding-left: 80rpx;
			}
		}
		.BtnConfirm{
			margin-top: 150rpx;
			display: flex;
			.BtnCancelOrder{
				width: 250rpx;
				margin-bottom: 30rpx;
				border-radius: 50rpx;
				border: 3rpx solid darkgray;
				margin-right: 15rpx;
			}
			.BtnPayOrder{
				background-color: $uni-color-selected;
				color: $uni-text-color-inverse;
				margin-left: 15rpx;
				width: 250rpx;
				margin-bottom: 30rpx;
				border-radius: 50rpx;
				// border: 3rpx solid darkgray;
			}
		}
		.ConfirmGetGoods{
			margin-top: 150rpx;
			margin-bottom: 50rpx;
			.BtnConfirmGetGoods{
				background-color: $uni-color-selected;
				color: $uni-text-color-inverse;
				margin: 50rpx 5%;
				width: 90%;
				border-radius: 50rpx;
				height: 100rpx;
				line-height: 100rpx;
			}
		}
	}
	.line{
		background-color: $uni-bg-color-grey;
		height: 20rpx;
	}
	.lineOne{
		background-color: $uni-bg-color-grey;
		height: 5rpx;
		width: 94%;
		margin: 3%;
	}
	

</style>
