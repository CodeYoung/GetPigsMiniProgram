<template>
	<view>
		<view class="goods_item">
			<!-- 用户信息 -->
			<view class="headerInfo">
				<!-- <image class="userHeaderImg" src="../static/other/蒙版组 1.png"></image> -->
				<image class="userHeaderImg" :src="goods.HeaderImg"></image>
				<view class="userInfo">
					<view class="userName">{{goods.UserName}}</view>
					<!-- <view class="goods_date">{{goods.ToSellData}}</view> -->
				</view>
			</view>
			<!-- 商品信息 -->
			<view class="goodsInfos">
				<view class="goodsInfo">
					<view class="goodsInfoHead">类别</view>
					<view class="goodsInfoText">{{goods.name}}</view>
				</view>
				<view class="goodsInfo">
					<view class="goodsInfoHead">可卖数量</view>
					<view class="goodsInfoText">{{goods.kcsl}}{{goods.kcslunit}}</view>
				</view>
				<view class="goodsInfo">
					<view class="goodsInfoHead">平均重量</view>
					<view class="goodsInfoText">{{goods.avgweight}}{{goods.weightunit}}</view>
				</view>
				<view class="goodsInfo">
					<view class="goodsInfoHead">期望价格</view>
					<view class="goodsInfoText">{{goods.price}}{{goods.priceunit}}</view>
				</view>
			</view>
			<!-- 商品详细信息 -->
			<view class="goodsDetails">
				<view class="goodsMemo">{{goods.memo}}</view>
				<view class="goodsImgs" >
					<view class="goodsImg" v-for="item in goods.GoodsImgs" :key="item.id">
						<image class="goodsImgShow" :src="item.url"></image>
					</view>
					
				</view>
			</view>
			<!-- 其他信息 -->
			<view class="otherInfo">
				<view class="location">
					<image src="../static/icon/location.png" class="locationImg"></image>
					<view class="locationText">重庆渝北</view>
					<view class="scanInfo">{{goods.ScanCount}}</view>
				</view>
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"goodsItemControl",
		data() {
			return {
				
			};
		},
		mounted() {
			
		},
		
		props:['goods']
	}
</script>

<style lang="scss">
.headerInfo{
	margin: 0 10px ;
	height: 50px;
	display: flex;
	.userHeaderImg{
		height: 40px;
		width: 40px;
	}
	.userInfo{
		margin-left: 10rpx;
		.userName{
			font-weight: bold;
		}
		.goods_date{
			background-color: #00aa00;
			color: $uni-text-color-inverse;
			width: 80rpx;
			border-radius: 10rpx;
			text-align: center;
		}
	}
}

.goodsInfos{
	display: flex;
	background-color: $uni-bg-color-darkgrey;
	border-radius: 10rpx;
	margin: 0 10px ;
	.goodsInfo{
		width: 25%;
		text-align: center;
		
		.goodsInfoHead{
			font-size: $uni-font-size-base;
			color: $uni-text-color-grey;
		}
		.goodsInfoText{
			font-weight: bold;
		}
	}
	
}

.goodsDetails{
	margin: 10px 10px ;
	.goodsImgs{
		display: flex;
		// flex-direction: row;
		flex-wrap: wrap;
		// justify-content: space-between;
		// place-items: ;
		 // background-color: black;
		.goodsImg{
			border-radius: 20rpx;
			display: flex;
			margin-right: 20rpx;
			// flex-direction: column;
			width: 200rpx;
			 // background-color: black;
			.goodsImgShow{
				width: 200rpx;
				height: 200rpx;
			}
			// margin: 10rpx;
		}
	}
	
}
.otherInfo{
	.location{
		
		display: flex;
		// flex-direction: row;
		.locationImg{
			padding-top: 10rpx;
			width: 30rpx;
			height: 30rpx;
		}
		.locationText{
			color: #0066CC;
		}
		.scanInfo{
			margin-left: 150px;
			color: $uni-text-color-grey;
			// margin-right: 10rpx;
		}
	}
}

</style>