<template>
	<view class="thispage">
		<view class="UserInfo">
			<image class="UserHeaderImg" :src="userInfo.userHeaderImg"></image>
			<text class="UserName">{{userInfo.userName}}</text>
		</view>
		<view class="MyOrderList">
			<view class=MyOrderListTitle>
				<text class="MyOrderListHeader">我的订单</text>
				<button class="BtnAllOrderList" size="mini">全部订单 ></button>
				<!-- <Navbar right-icon="right" title="全部订单" @clickLeft="back" /> -->
				<!-- <Navbar ></Navbar> -->
			</view>
			<view class=MyOrderListTypes>
				<view class="ToPayBox">
					<button class="ToPay">
						<image class="ToPayImg" src="../../static/icon/card.png"></image>
					</button>
					<text class="ToPayText">待付款</text>
				</view>
				<view class="ToExpressBox">
					<button class="ToExpress">
						<image class="ToExpressImg" src="../../static/icon/package.png"></image>
					</button>
					<text class="ToExpressText">待付款</text>
				</view>
				<view class="ToGetGoodsBox">
					<button class="ToGetGoods">
						<image class="ToGetGoodsImg" src="../../static/icon/right.png"></image>
					</button>
					<text class="ToGetGoodsText">待付款</text>
				</view>
			</view>
		</view>
		
		<view class="NavList">
			<image class="navIcon" src="../../static/icon/组 97.png"></image>
			<view>
				<Navbar class="navBar" left-width="190px" right-icon="right"  left-text="我的发布" @clickLeft="back" />
			</view>
		<image class="navIcon" src="../../static/icon/group.png"></image>
		<view>
			<Navbar class="navBar" left-width="190px" right-icon="right"  left-text="申请成为老板" @clickLeft="back" />
		</view>
		<image class="navIcon" src="../../static/icon/message.png"></image>
		<view>
			<Navbar class="navBar" left-width="190px" right-icon="right"  left-text="平台客服" @clickLeft="back" />
		</view>
		<image class="navIcon" src="../../static/icon/group_1.png"></image>
		<view>
			<Navbar class="navBar" left-width="190px" right-icon="right"  left-text="养殖交流群" @clickLeft="back" />
		</view>
		</view>
	</view>
</template>

<script>
	import Navbar from "../../uni_modules/uni-nav-bar/components/uni-nav-bar/uni-nav-bar"
	export default {

		data() {
			return {
				userInfo: {
					id: 1,
					userHeaderImg: "../../static/other/蒙版组 1.png",
					userName: "He柒月的阿卡莎"
				}
			}
		},
		components: {
			Navbar
		}
	}
</script>


<style lang="scss">
	// @import url(../../uni_modules/uni-icons/components/uni-icons/uniicons.css);
	.thispage {
		background-color: $uni-bg-color-grey;
		height: 1200rpx;
		padding: 10rpx;

		.UserInfo {
			display: flex;
			margin-top: 50rpx;
			margin-left: 50rpx;

			.UserHeaderImg {
				height: 100rpx;
				width: 100rpx;
			}

			.UserName {
				height: 100rpx;
				margin-left: 20rpx;
				padding-top: 30rpx;
				font-weight: bold;
			}
		}

		.MyOrderList {
			height: 300rpx;
			background-color: $uni-bg-color;
			margin: 20rpx;
			border-radius: 30rpx;

			.MyOrderListTitle {

				display: flex;

				// margin-left: 120rpx;
				.MyOrderListHeader {
					margin: 20rpx;
					font-weight: bold;
					// background-color: red;
					padding-top: 10rpx;
					// width: 80rpx;
				}

				.BtnAllOrderList {
					text-align: right;
					line-height: 80rpx;
					padding-right: 20rpx;
					height: 80rpx;
					width: 200rpx;
					margin-top: 20rpx;
					margin-left: 285rpx;
					border: none;
					background-color: transparent;
					color: $uni-text-color-disable;
				}

				.BtnAllOrderList::after {
					border: none;
				}
			}

			.MyOrderListTypes {
				display: flex;
				.ToPayBox {
					margin:30rpx 50rpx;
					.ToPay {
						// display: flex;
						// flex-direction: column;
						height: 80rpx;
						width: 120rpx;

						.ToPayImg {
							height: 50rpx;
							width: 50rpx;
						}

						
					}
					.ToPayText {
						padding-left: 15rpx;
					}
				}

				.ToExpressBox {
					margin:30rpx 50rpx;
					.ToExpress {
						// display: flex;
						// flex-direction: column;
						height: 80rpx;
						width: 120rpx;

						.ToExpressImg {
							height: 50rpx;
							width: 50rpx;
						}

						
					}
					.ToExpressText {
						padding-left: 15rpx;
					}
				}

				.ToGetGoodsBox {
					margin:30rpx 50rpx;
					.ToGetGoods {
						// display: flex;
						// flex-direction: column;
						height: 80rpx;
						width: 120rpx;

						.ToGetGoodsImg {
							height: 50rpx;
							width: 50rpx;
						}

						
					}
					.ToGetGoodsText {
						padding-left: 15rpx;
					}
				}


			}

		}
	.NavList{
		background-color: $uni-bg-color;
		display: flex;
		margin: 20rpx;
		flex-wrap: wrap;
		.navIcon{
			width: 40rpx;
			height: 40rpx;
			margin-top: 25rpx;
			margin-left: 30rpx;
		}
		.navBar{
			font-size: 40rpx;
		}
	}
	}
</style>
