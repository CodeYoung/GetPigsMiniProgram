<template>
	<view class="home">
		<scroll-view>
			<swiper circular class="swiperImg" >
					<swiper-item v-for="item in goods.GoodsImgs" :key="item.id">
						<image :src="item.url"></image>
					</swiper-item>
			</swiper>
		</scroll-view>

		<view class="goodsName">{{goods.name}}</view>
		<view class="sellInfo">
			<view class="goodsPrice">￥{{goods.price}}</view>
			<view class="sellcount">已售{{goods.scancount}}</view>
		</view>
		<view class="tips">正品兽药    ·    假一赔十   ·   免费包邮</view>
		<view class="goodsDetails">
			<view class="goodsDetailsBox"></view>
			<view class="goodDetailsHead">------商品详情------</view>
			<view class="goodsMemo">{{goods.memo}}</view>
		</view>
		<view>
			<button class="btnBuy">立即购买</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				goods:{}
			}
		},
		onload()
		{
			console.log("页面加载")
			this.getGoods(1)
		},
		onShow() {
			this.getGoods(1)
		},
		methods: {
			async getGoods(goodsid)
			{
				const res= await this.$myRequest({
					url:'/Api/pigApi/GetGoods',
					method:'POST',
					data:{'id':goodsid}
				})
				this.goods=res.data.data
			}
		}
	}
</script>

<style lang="scss">
.home{
	swiper{
		width: 750rpx;
		height: 380rpx;
		image{
			height: 100%;
			width: 100%;
		}
	}
	.sellInfo{
		display: flex;
		.goodsPrice{
			margin-top: 10rpx;
			color: red;
			// font-size:15px;
			font-weight: bold;
		}
		.sellcount{
			color: $uni-text-color-grey;
			padding-top: 15rpx;
			margin-left: 220px;
		}
	}
	
	.goodsName{
		margin-top: 10rpx;
		// margin-left: 300rpx;
		// font-size:15px;
		font-weight: bold;
		text-align: center;
		width: 100%;
	}
	
	.goodsDetails{
		
		margin-top: 10rpx;
		background-color: $uni-bg-color-grey;
		.goodsDetailsBox{
			padding-top: 20rpx;
		}
		.goodDetailsHead{
			background-color: white;
			text-align: center;
		}
		.goodsMemo{
			background-color: white;
			padding: 30rpx;
			color: $uni-text-color-grey;
		}
		
	}
	.tips{
		margin-top: 20rpx;
		margin-left: 35rpx;
		text-align: center;
		padding-top: 20rpx;
		color: $uni-text-color-grey;
		background-color: $uni-bg-color-grey;
		width: 90%;
		height: 70rpx;
		border-radius: 10rpx;
	}
	.btnBuy{
		position: fixed;
		bottom: 0rpx;
		width: 80%;
		margin: 10%;
		background-color: $uni-color-selected;
		border-radius: 50rpx;
		color: $uni-text-color-inverse;
	}
}
</style>
