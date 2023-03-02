<template>
	<view class="thispage">
		<scroll-view>
			<swiper circular indicator-dots class="swiperImg">
				<swiper-item v-for="item in goodsImgs" :key="item.id">
					<image :src="item.url"></image>
				</swiper-item>
			</swiper>
		</scroll-view>

		<!-- 内容显示区域 -->
		<!-- <scroll-view> -->
		<tabControl :category='category' @ChangeTab='ChangeTab'></tabControl>
		<view class="goods_list">
			<view class="goods_item" v-for="item in goodsList" :key="item.id">
				<image class="goodsImg" :src="item.goodsImgUrl"></image>
				<view class="goodsName">{{item.name}}</view>
				<view class="goodSellInfo">
					<text class="goodsPrice">{{item.price}}</text>
					<text class="goodsScanCount">{{item.scanCount}}</text>
				</view>
			</view>
		</view>
		<button class="AskAnimalDoctor">
			<!-- <image src=""></image> -->
			免费咨询兽医
			</button>
		<!-- </scroll-view> -->
	</view>
</template>

<script>
	import tabControl from "../../components/tabControl.vue"
	export default {
		data() {
			return {
				goodsImgs: [{
						id: 1,
						url: "http://qiniu.nineorange.cn/goodsImgs/%E8%92%99%E7%89%88%E7%BB%84%202.png"
					},
					{
						id: 2,
						url: "http://qiniu.nineorange.cn/goodsImgs/%E8%92%99%E7%89%88%E7%BB%84%203.png"
					}
				],
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
				goodsList: [{
					id: 1,
					name: "复合维生素B兽用注射液",
					goodsImgUrl: "http://qiniu.nineorange.cn/goodsImgs/%E8%92%99%E7%89%88%E7%BB%84%203.png",
					price: "￥25.8",
					scanCount: "已售317"
				}, {
					id: 2,
					name: "复合维生素B兽用注射液",
					goodsImgUrl: "http://qiniu.nineorange.cn/goodsImgs/%E8%92%99%E7%89%88%E7%BB%84%203.png",
					price: "￥25.8",
					scanCount: "已售317"
				}, {
					id: 3,
					name: "复合维生素B兽用注射液",
					goodsImgUrl: "http://qiniu.nineorange.cn/goodsImgs/%E8%92%99%E7%89%88%E7%BB%84%203.png",
					price: "￥25.8",
					scanCount: "已售317"
				}]
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
		overflow: hidden;

		swiper {
			width: 750rpx;
			height: 380rpx;

			image {
				height: 100%;
				width: 100%;
			}
		}

		.goods_list {
			padding: 20rpx 40rpx;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;

			.goods_item {
				// display: flex;
				// flex-direction: column;

				width: 330rpx;
				margin: 20rpx 0;

				.goodsImg {
					width: 100%;
					height: 250rpx;
				}

				.goodsPrice {
					font-weight: bold;
					color: red;
				}

				.goodsScanCount {
					color: $uni-text-color-disable;
					font-size: 20rpx;
					margin-left: 20rpx;
				}

			}
		}

		.AskAnimalDoctor {
			position: fixed;
			bottom: 50px;
			width: 90%;
			margin: 5%;
			border-radius: 60rpx;
			background-color: $uni-color-selected;
			color: $uni-text-color-inverse;
		}


	}
</style>
