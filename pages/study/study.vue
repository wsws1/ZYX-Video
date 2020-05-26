<style>
	page{
		background-color:#F8F8F8;
	}
	.title{
		display: flex;
		background-color: #F8F8F8;
		height: 62rpx;
		padding: 0rpx 40rpx;
		font-size: 30rpx;
		font-weight: 700;
	}
	.title view{
		color: #999999;
		margin-right: 10rpx;
		transition: 0.3s;
	}
	.title text:nth-of-type(1){
		margin-right: 30rpx;
	}
	.active{
		position: relative;
		color: black !important;
		font-size: 31rpx;
		font-weight: 700;
	}
	.active::before{
		content: "";
		position: absolute;
		width: 20rpx;
		height: 8rpx;
		background-color: #000000;
		left: 50rpx;
		border-radius: 25rpx;
		bottom: 0rpx;
	}
	.content{
		padding: 0rpx 20rpx;
	}
	.collet_buy{
		margin-top: 20rpx;
		width: 100%;
		height: 180rpx;
		background-color: white;
		border-radius:20rpx;
		padding: 0rpx 20rpx;
		box-sizing: border-box;
	}
	.collet_buy text{
		color: black;
		font-size: 30rpx;
		font-weight: 700;
	}
	.collet,.buy{
		height: 90rpx;
		line-height: 90rpx;
	}
	.collet{
		border-bottom: 1px solid #f0f0f0;
	}
	.lately_study{
		margin-top: 20rpx;
		width: 100%;
		background-color: white;
		border-radius:20rpx;
		padding: 20rpx;
		box-sizing: border-box;
	}
	.lately_study text{
		color: #000000;
		color: black;
		font-size: 30rpx;
		font-weight: 700;
	}
	.download{
		margin-top: 20rpx;
		width: 100%;
		background-color: white;
		border-radius:20rpx;
		padding: 20rpx;
		box-sizing: border-box;
	}
	.download text{
		color: #000000;
		font-size: 30rpx;
		font-weight: 700;
	}
	.study_notes{
		margin-top: 20rpx;
		width: 100%;
		height: 150rpx;
		background-color: white;
		border-radius:20rpx;
		padding: 20rpx;
		box-sizing: border-box;
	}
	.study_notes{
		display: flex;
		justify-content: space-between;
	}
	.study_notes image{
		width: 55rpx;
		height: 55rpx;
	}
	.study_item{
		text-align: center;
	}
	.study_item .icon{
		font-size: 24rpx;
	}
	.collet,
	.buy,
	.lately_study,
	.download{
		display: flex;
		justify-content: space-between;
	}
</style>
<template>
	<view class="container">
		<view class="title">
			<view @click="choice(index)" :class="{'active':current==index}" v-for="(item,index) in curriculum" :key="index">{{item}}</view>
		</view>
		<view class="content">
			<view class="collet_buy">
				<view class="collet"><text>我的收藏</text><text class="icon-arrow-down iconfont"></text></view>
				<view class="buy"><text>我的购买</text><text class="icon-arrow-down iconfont"></text></view>
			</view>
			<view class="lately_study"><text>最近学习</text><text class="icon-arrow-down iconfont"></text></view>
			<view class="download"><text>下载管理</text><text class="icon-arrow-down iconfont"></text></view>
			<view class="study_notes">
				<view class="study_item">
					<image src="../../static/ziyuan.png" mode="aspectFit"></image>
					<view class="icon">我的笔记</view>
				</view>
				<view class="study_item">
					<image src="../../static/wode.png" mode="aspectFit"></image>
					<view class="icon">我的问答</view>
				</view>
				<view class="study_item">
					<image src="../../static/wodebiji.png" mode="aspectFit"></image>
					<view class="icon">我的手记</view>
				</view>
				<view class="study_item">
					<image src="../../static/meiriqiandao.png" mode="aspectFit"></image>
					<view class="icon">每日签到</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data() {
			return {
				curriculum:["我的课程","我的课表"],
				index:0,
				current:0
			}
		},
		methods: {
			choice(index){
				this.index=index,
				this.current=index
			}
		},
	}
</script>


