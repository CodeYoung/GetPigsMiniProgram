<template>
	<view class="thispage">
		<tabControl :category='category' isWhite=true @ChangeTab='ChangeTab'></tabControl>
		<view class="goods_list">
			<scroll-view class="goods_item" v-for="item in goodsList" :key="item.Id">
				<goodsItemControl  :goods='item'></goodsItemControl>
				<button class="BtnTakeOrder">立即接单</button>
			</scroll-view> 
				
		</view>
	</view>
</template>

<script>
	import tabControl from "../../components/tabControl.vue"
	import goodsItemControl from "../../components/goodsItemControl.vue"
	export default {
		onShow() {
			uni.setNavigationBarTitle({
			                     title: this.userInfo.name
			                 });
							 
		},
		data() {
			return {
				category: [{
						id: 1,
						name: '待接单',
					},
					{
						id: 2,
						name: '已接单',
					},
					{
						id: 3,
						name: '已完成',
					},
				],
				userInfo:{
					id:1,
					name:"老板昵称"
				},
				goodsList:[],
			}
		},
		methods: {
			ChangeTab(currentTabindex){
				//getGoodsList(currentTabindex)
				 console.log('当前选择页'+currentTabindex);
				 this.getGoodsList(currentTabindex);
			},
			async getGoodsList(currentTabindex) {
			 const res= await this.$myRequest({
					url:'/Api/pigApi/GetGoodsList',
					method:'POST',
					data:{"goodsType":currentTabindex+1}
				})
				this.goodsList=res.data.data
				console.log(res)
			}
		},
		components:{
			tabControl,
			goodsItemControl
		}
	}
</script>

<style lang="scss">
	.thispage{
		.goods_list
		{
			margin-top: 60rpx;
			background-color: $uni-bg-color-grey;
			.goods_item{
				background-color: $uni-bg-color;
				margin-top: 10rpx;
				padding-bottom: 30rpx;
				.BtnTakeOrder{
					width: 90%;
					margin: 10rpx 5%;
					border-radius: 60rpx;
					background-color: $uni-color-selected;
					color: $uni-text-color-inverse;
					// padding: 0 0%;
				}
			}
		}
	}
</style>
