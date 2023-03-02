<template>
	<view class="thispage">
		<view class="line"></view>
		<view class="headerInfo">
			<!-- <image class="userHeaderImg" src="../static/other/蒙版组 1.png"></image> -->
			<image class="userHeaderImg" :src="goods.HeaderImg"></image>
			<view class="userInfo">
				<view class="userName">
					<text decode>{{goods.UserName}}</text>

				</view>
				<view class="goods_date">{{goods.ToSellDate}}</view>
			</view>
		</view>
		<view class="line" style="margin: 0 30rpx;"></view>
		<view class="OrderGoodsInfo" v-for="item in goods.GoodsInfos">
			<view class="InfoHead">{{item.InfoHead}}</view>
			<view class="InfoText">{{item.InfoText}}</view>
		</view>
		<view class="line" style="margin: 0 30rpx;"></view>
		<!-- 商品详细信息 -->
		<view class="goodsDetails">
			<view class="goodsMemo">{{goods.memo}}</view>
			<view class="goodsImgs">
				<view class="goodsImg" v-for="item in goods.GoodsImgs" :key="item.id">
					<image class="goodsImgShow" :src="item.url"></image>
				</view>

			</view>
		</view>
		<!-- 其他信息 -->
		<view class="otherInfo">
			<view class="location">
				<image src="../../static/icon/location.png" class="locationImg"></image>
				<view class="locationText">重庆渝北</view>
			</view>

		</view>
		<view class="line"  ></view>
		<view class="LxrInfo">
			<view class="LxrName">联系人：{{goods.LxrInfo.Name}}</view>
			<view class="LxrPhone">电话：{{goods.LxrInfo.LxrPhone}}</view>
		</view>
		<view class="LxrTips">联系时请告知在收猪啦平台上面看到的</view>
		<view class="line" style="height: 40rpx;margin: 0 40rpx;"></view>
		<view class="OrderTips">
			<view class="WarnText">如遇无效、虚假、诈骗信息，请立即举报</view>
			<view class="WarnTips">请自行甄别卖家信息，发现虚假请第一时间举报，本站无责任核实信息真伪，后果需自行承担。</view>
		</view>
		<view class="line"  style="margin-top: 30rpx;"></view>
		<view class="ButtonBox">
			<button class="BtnCancelOrder" v-show="!isShowTakeOrder">取消订单</button>
			<button class="BtnFinishOrder" v-show="!isShowTakeOrder">完成订单</button>
			<button class="BtnPhoneCall" v-show="!isShowTakeOrder">
				<image style="height: 80rpx;width: 200rpx;" src="../../static/other/组 278.png"></image>
			</button>
			<button class="BtnTakeOrder" v-show="isShowTakeOrder">立即接单</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				goods: {
					HeaderImg: "http://qiniu.nineorange.cn/headerImgs/%E8%92%99%E7%89%88%E7%BB%84%201.png",
					UserName: "天猪工厂",
					ToSellDate: "2023-02-15",
					GoodsInfos: [{
						InfoHead: "类      别",
						InfoText: "育肥猪"
					}, {
						InfoHead: "可卖数量",
						InfoText: "12头"
					}, {
						InfoHead: "平均重量",
						InfoText: "260斤"
					}, {
						InfoHead: "期望价格",
						InfoText: "10元/斤"
					}],
					memo:"大量成猪",
					GoodsImgs:[{id:"1",url:"http://qiniu.nineorange.cn/goodsImgs/%E8%92%99%E7%89%88%E7%BB%84%202.png"},{id:"2",url:"http://qiniu.nineorange.cn/goodsImgs/%E8%92%99%E7%89%88%E7%BB%84%203.png"}],
					LxrInfo:{
						Name:"张三",
						LxrPhone:"15889268163"
					}
				},
				isShowTakeOrder:true
				
			}
		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.thispage {
		.headerInfo {
			margin: 20px;
			height: 50px;
			display: flex;

			.userHeaderImg {
				height: 40px;
				width: 40px;
			}

			.userInfo {
				margin-left: 10rpx;

				.userName {
					font-weight: bold;
				}

				.goods_date {
					// background-color: $uni-text-color-disable;
					color: $uni-text-color-disable;
					font-size: 10rpx;
					width: 180rpx;
					border-radius: 10rpx;
					padding-top: 10rpx;
					text-align: left;
				}
			}
		}

		.OrderGoodsInfo {
			background-color: $uni-bg-color-grey;
			margin: 0 30rpx;
			display: flex;

			.InfoHead {
				// background-color: gray;
				// height: 30rpx;
				margin: 0rpx 30rpx;
				width: 130rpx;
				padding-top: 10rpx;
				padding-bottom: 10rpx;
				white-space: pre-wrap;
				// justify-content: space-between;
				color: $uni-text-color-disable;
			}

			.InfoText {
				padding-top: 10rpx;
				// margin: 30rpx;
				// height: 30rpx;
			}
		}

		.goodsDetails {
			margin: 10px 10px;

			.goodsImgs {
				display: flex;
				// flex-direction: row;
				flex-wrap: wrap;

				// justify-content: space-between;
				// place-items: ;
		 	// background-color: black;
				.goodsImg {
					border-radius: 20rpx;
					display: flex;
					margin-right: 20rpx;
					// flex-direction: column;
					width: 200rpx;

					// background-color: black;
					.goodsImgShow {
						width: 200rpx;
						height: 200rpx;
					}

					// margin: 10rpx;
				}
			}

		}

		.otherInfo {
			.location {

				display: flex;

				// flex-direction: row;
				.locationImg {
					padding-top: 10rpx;
					width: 30rpx;
					height: 30rpx;
				}

				.locationText {
					color: #0066CC;
				}

				.scanInfo {
					margin-left: 150px;
					color: $uni-text-color-grey;
					// margin-right: 10rpx;
				}
			}
		}

		.LxrInfo{
			margin-top: 40rpx;
			background-color: $uni-bg-color-grey;
			margin-left: 40rpx;
			margin-right: 40rpx;
			display: flex;
			.LxrName{
				margin: 20rpx 40rpx;
				font-weight: bold;
			}
			.LxrPhone{
				margin-top: 20rpx;
				margin-left:  50rpx;
				font-weight: bold;
			}
		}
		.LxrTips{
			background-color: $uni-bg-color-grey;
			margin-left: 40rpx;
			margin-right: 40rpx;
			padding-left: 40rpx;
			font-size: 30rpx;
			color:red;
		}
		.OrderTips{
			margin-top: 30rpx;
			margin-left: 30rpx;
			.WarnText{
				font-weight: bold;
				color: red;
			}
			.WarnTips{
				margin-top: 20rpx;
				margin-right: 40rpx;
				color: $uni-text-color-disable;
				font-size: 26rpx;
			}
		}
		.ButtonBox{
			display: flex;
			height: 120rpx;
			margin-top: 60rpx;
			.BtnCancelOrder{
				height: 80rpx;
				border-radius: 60rpx;
				line-height: 80rpx;
				border: 2rpx solid lightgray;
			}
			.BtnFinishOrder{
				height: 80rpx;
				border-radius: 60rpx;
				background-color: $uni-color-selected;
				line-height: 80rpx;
				color: $uni-text-color-inverse;
			}
			.BtnPhoneCall{
				height: 80rpx;
				padding-left: 0rpx;
				padding-right: 0rpx;
				border-radius: 60rpx;
				// width: 200rpx;
			}
			.BtnTakeOrder{
				height: 80rpx;
				width: 90%;
				border-radius: 60rpx;
				background-color: $uni-color-selected;
				line-height: 80rpx;
				color: $uni-text-color-inverse;
			}
		}
		.line {
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
