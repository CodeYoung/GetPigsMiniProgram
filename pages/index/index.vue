<template>
	<view class="topContent">
		<view class="todayPrice">今日猪价 {{today}}已更新</view>
		<view class="boxs">
			<view class="box" style="">
				<view style="color: black;padding-left: 45rpx;padding-top: 20rpx;font-size: 30rpx;">外三元</view>
				<view
					style="color: red;padding-left: 25rpx;padding-top: 10rpx;padding-bottom: 10rpx; font-size: 50rpx;">
					16.27</view>
				<view class="boxs">
					<view style="color: gray;font-size: 30rpx;">较昨日 </view>
					<view style="color: red;font-size: 30rpx;">+0.23 </view>
				</view>
			</view>
			<view class="box" style="">
				<view style="color: black;padding-left: 45rpx;padding-top: 20rpx;font-size: 30rpx;">内三元</view>
				<view
					style="color: red;padding-left: 25rpx;padding-top: 10rpx;padding-bottom: 10rpx; font-size: 50rpx;">
					15.36</view>
				<view class="boxs">
					<view style="color: gray;font-size: 30rpx;">较昨日 </view>
					<view style="color: red;font-size: 30rpx;">+0.09 </view>
				</view>
			</view>
			<view class="box" style="">
				<view style="color: black;padding-left: 45rpx;padding-top: 20rpx;font-size: 30rpx;">土杂猪</view>
				<view
					style="color: red;padding-left: 25rpx;padding-top: 10rpx;padding-bottom: 10rpx; font-size: 50rpx;">
					14.79</view>
				<view class="boxs">
					<view style="color: gray;font-size: 30rpx;">较昨日 </view>
					<view style="color: red;font-size: 30rpx;">+0.87 </view>
				</view>
			</view>
		</view>
		<view class="message">
			<image src="../../static/icon/voice_1.png" style="height: 30rpx;width: 30rpx;margin-right: 20rpx;"></image>
			<view>用户xx土杂猪出售成功 订单已完成...</view>
		</view>
		<tabControl :category='category' @ChangeTab='ChangeTab'></tabControl>
	</view>
</template>

<script>
	import tabControl from "../../components/tabControl.vue"
	export default {
		watch: {
			// swiper与上面选项卡联动
			currentindex(newval) {
				console.log(newval);
				this.isActive = newval;
				this.scrollLeft = 0;
				// 滑动swiper后，每个选项距离其父元素最左侧的距离
				for (let i = 0; i < newval - 1; i++) {
					this.scrollLeft += this.category[i].width
				};
			},
		},
		data() {
			return {
				today: '',
				isActive: 0,
				index: 0,
				currentindex: 0,
				category: [{
						id: 1,
						name: '全部',
					},
					{
						id: 2,
						name: '猪',
					},
					{
						id: 3,
						name: '牛',
					},
					{
						id: 4,
						name: '羊',
					},
					// {
					// 	id: 5,
					// 	name: '选项卡五',
					// },
					// {
					// 	id: 6,
					// 	name: '选项卡六',
					// },
				],
				contentScrollW: 0, // 导航区宽度
				scrollLeft: 0, // 横向滚动条位置
				fullHeight: "",
			}
		},
		mounted() {
			this.currentTime();
			var that = this;
			//获取手机屏幕的高度，让其等于swiper的高度，从而使屏幕充满
			uni.getSystemInfo({
				success: function(res) {
					that.fullHeight = "height:" + res.windowHeight + "px";
				}
			});

		},
		onLoad() {
			this.currentTime();
		},
		methods: {
			
			currentTime() {
				setInterval(this.getDate, 500);
			},
			getDate() {
				var _this = this;
				let yy = new Date().getFullYear();
				let mm = new Date().getMonth() + 1;
				let dd = new Date().getDate();
				let week = new Date().getDay();
				let hh = new Date().getHours();
				let ms =
					new Date().getSeconds() < 10 ?
					"0" + new Date().getSeconds() :
					new Date().getSeconds();
				let mf =
					new Date().getMinutes() < 10 ?
					"0" + new Date().getMinutes() :
					new Date().getMinutes();
				if (week == 1) {
					this.nowWeek = "星期一";
				} else if (week == 2) {
					this.nowWeek = "星期二";
				} else if (week == 3) {
					this.nowWeek = "星期三";
				} else if (week == 4) {
					this.nowWeek = "星期四";
				} else if (week == 5) {
					this.nowWeek = "星期五";
				} else if (week == 6) {
					this.nowWeek = "星期六";
				} else {
					this.nowWeek = "星期日";
				}
				//_this.nowTime = hh + ":" + mf + ":" + ms;
				//_this.nowDate = yy + "-" + mm + "-" + dd;
				//_this.$data.today=yy + "-" + mm + "-" + dd;
				_this.today = yy + "-" + mm + "-" + dd;
			},
			ChangeTab(currentTabindex){
				// console.log('当前选择页'+currentTabindex);
			}

		},
		components:{
			tabControl
		}
	}
</script>

<style>
	/* page{
        height: 100%;
        display: flex;
        background-color: #FFFFFF;
    } */
	.topContent {

		background-color: #FF8C00;
		height: 370rpx;

	}

	.todayPrice {
		color: #DCDCDC;
		font-size: 30rpx;
		padding-left: 30rpx;
	}

	.boxs {
		display: flex;
		flex-direction: row;
		padding-left: 10rpx;
		padding-right: 10rpx;
	}

	.box {
		width: 33.33%;
		height: 200rpx;
		padding-left: 10rpx;
		margin: 20rpx;
		background-color: white;
		border-radius: 20rpx;
	}

	.message {
		margin-top: 50rpx;
		margin-left: 5%;
		margin-bottom: 10rpx;
		background-color: white;
		width: 90%;
		height: 80rpx;
		border: gray;
		border-radius: 3px;
		box-shadow: 1px 1px 2px 2px rgba(0, 0, 0, 0.1);
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
	}
	
	
</style>
