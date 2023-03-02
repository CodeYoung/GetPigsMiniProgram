<template>
	<view class="thispage">
		<view class="NoOrders" v-show="NoOrders">
			<image class="OrderImage" src="../../static/icon/add_1.png"></image>
			<view class="Nothing">暂无订单~</view>
		</view>
		<tabControl :category='category' v-show="!NoOrders" @ChangeTab='ChangeTab'></tabControl>
		<view class="OrderList" v-show="!NoOrders" v-for="item in OrderList" :key="item.id">
			<view class="OrderItem">
				<view class="OrderInfo">
					<text class="OrderNum">订单号：{{item.id}}</text>
					<text class="OrderStatus">{{item.statusName}}</text>
				</view>
				<view class="OrderGoodsInfo">
					<image class="OrderGoodsImg" :src="item.goodsImgUrl"></image>
					<view class="OrderGoodsSellInfo">
						<view>{{item.name}}</view>
						<view class="OrderGoodsSellDetailInfo">
							<view>
								<text class="OrderGoodsSellPrice">{{item.price}}</text>
								<text class="OrderGoodsSellCount">{{item.count}}</text>
							</view>
						</view>
					</view>
				</view>
				<view class="lineOne"></view>
				<view class="OrderPayInfoNeedPay" v-show="IsNeedPay">
					<text style="font-size: 18rpx;">剩余支付时间</text>
					<text class="payLimitTime">{{item.payLimitTime}}</text>
					<text style="padding-left: 100rpx;">合计待付款:</text>
					<text class="totalMoney">{{item.totalMoney}}</text>
					<view class="OrderButtons">
						<button>取消订单</button>
						<button>查看详情</button>
						<button>去支付</button>
					</view>
				</view>
				<view class="OrderButtons">
					<button>取消订单</button>
					<button>查看详情</button>
					<button>去支付</button>
					<button>确定收货</button>
				</view>
			</view>


		</view>
	</view>
</template>

<script>
	import tabControl from "../../components/tabControl.vue"
	export default {
		data() {
			return {
				category: [{
						id: 1,
						name: '全部',
					},
					{
						id: 2,
						name: '猪用药品',
					},
					{
						id: 3,
						name: '牛羊药品',
					},
					{
						id: 4,
						name: '禽用药品',
					},
					{
						id: 5,
						name: '兔用药品',
					}
				],
				NoOrders: false,
				OrderList: [{
					id: 1,
					statusName: "待付款",
					status: "1",
					goodsImgUrl: "../../static/other/蒙版组 9.png",
					name: "复合维生素兽用注射液猪牛羊用产后消炎",
					price: "￥25.8",
					count: "×1",
					totalMoney: "￥25.8",
					payLimitTime: "01时20分20分"

				}, {
					id: 2,
					statusName: "待发货",
					status: "2",
					goodsImgUrl: "../../static/other/蒙版组 9.png",
					name: "复合维生素兽用注射液猪牛羊用产后消炎",
					price: "￥25.8",
					count: "×1",
					totalMoney: "￥25.8",
					payLimitTime: "01时20分20分"

				}],
				IsNeedPay:true
			}
		},
		methods: {

		},
		components: {
			tabControl
		}
	}
</script>

<style lang="scss">
	.thispage {
		background-color: $uni-bg-color-grey;

		.NoOrders {
			.OrderImage {
				height: 150rpx;
				width: 150rpx;
				margin-top: 400rpx;
				margin-left: 300rpx;
			}

			.Nothing {
				margin-left: 42%;
				color: #D3D3D3;
			}
		}

		.OrderList {

			padding: 10rpx 20rpx;
			justify-content: space-between;

			.OrderItem {
				background-color: white;

				.OrderInfo {
					margin: 20rpx;
					padding-top: 20rpx;

					.OrderNum {
						font-weight: bold;
					}

					.OrderStatus {
						color: $uni-text-color-disable;
						font-size: 18rpx;
						margin-left: 450rpx;

					}
				}

				.OrderGoodsInfo {
					display: flex;
					margin-bottom: 20rpx;

					.OrderGoodsImg {
						margin: 0 20rpx;
						width: 200rpx;
						height: 200rpx;
					}

					.OrderGoodsSellInfo {
						.OrderGoodsSellDetailInfo {
							margin-top: 50rpx;

							.OrderGoodsSellCount {
								margin-left: 350rpx;
							}
						}

					}


				}

				.OrderPayInfoNeedPay {
					margin-left: 20rpx;
					padding-bottom: 20rpx;
					.payLimitTime{
						font-size: 18rpx;
						color: $uni-color-selected;
						padding-left: 10rpx;
					}
					.totalMoney{
						padding-left: 10rpx;
						color: red;
					}
					.OrderButtons{
						margin-left: 50rpx;
						display: flex;
						button{
							width: 40%;
							margin: 20rpx;
							font-size: 30rpx;
							border-radius: 60rpx;
							border: 1rpx solid lightgray;
						}
					}
					
				}

				// .OrderGoodsInfo{
				// 	display: ;
				// }
			}

		}

		.line {
			margin-top: 30rpx;
			background-color: $uni-bg-color-grey;
			height: 20rpx;
		}

		.lineOne {
			background-color: $uni-bg-color-grey;
			height: 3rpx;
			width: 94%;
			margin: 3%;
		}

	}
</style>
