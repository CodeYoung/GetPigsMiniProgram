<template>
	<view class="topContent">
		今日猪价{{today}}已更新
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				today: ''
			}
		},
		mounted() {
		   this.currentTime();
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
			        new Date().getSeconds() < 10
			          ? "0" + new Date().getSeconds()
			          : new Date().getSeconds();
			        let mf =
			        new Date().getMinutes() < 10
			          ? "0" + new Date().getMinutes()
			          : new Date().getMinutes();
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
				  _this.today=yy + "-" + mm + "-" + dd;
			    },

		}
	}
</script>

<style>
	.topContent
	{
		color: green;
	}
</style>
