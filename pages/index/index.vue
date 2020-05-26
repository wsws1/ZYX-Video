<style>
	.container{
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 100vw;
	}
	.title{
		display: flex;
		justify-content: space-between;
		margin-top: 10rpx;
		font-size: 30rpx;
		font-weight: 700;
		padding: 0rpx 50rpx;
		height: 25px;
	}
	.title uni-list-item{
		background-color: #C0C0C0;
	}
	.title view{
		transition: 0.5s;
	}
	.active{
		position: relative;
		color: #dd1705;
		font-size: 31rpx;
		font-weight: 700;
	}
	.active:before{
		content: "";
		position: absolute;
		width: 20rpx;
		height: 8rpx;
		background-color: #dd1705;
		top: 50rpx;
		left: 35%;
		border-radius: 15rpx;
	}
	.get_job {
		padding: 0rpx 20rpx;
		display: flex;
		align-items: center;
		margin: 20rpx 0rpx;
	}
	.get_job text:nth-child(1){
		font-size: 35rpx;
		font-weight: 700;
		text-align: left;
	}
	.get_job text:nth-child(2){
		margin-left: 40rpx;
		font-size: 25rpx;
		color: #808080;
	}
	.technology{
		display: flex;
		justify-content: space-between;
		margin-top: 20rpx;
		box-shadow: 0rpx 2rpx 10rpx 0rpx #F0F0F0;
		padding: 20rpx 20rpx;
		margin: 0rpx 20rpx;
		border-radius: 10rpx;
	}
	.java,.html,.css,.javascipt{
		text-align: center;
		width: 155rpx;
		height: 100rpx;
		line-height: 100rpx;
		background-image: linear-gradient(45deg,rgb(6, 121, 252),rgb(120, 163, 228));
		border-radius: 10%;
		color: white;
		box-shadow: 3rpx 5rpx 10rpx 0rpx #CCCCCC;
		font-size: 26rpx;
	}
	.job_market{
		margin-top: 40rpx;
		padding: 0rpx 20rpx;
		display: flex;
		align-items: center;
		margin-bottom: 20rpx;
	}
	.job_market text:nth-child(1){
		font-size: 35rpx;
		font-weight: 700;
		text-align: left;
	}
	.job_market text:nth-child(2){
		margin-left: 40rpx;
		font-size: 25rpx;
		color: #808080;
	}
	.advance{
		display: flex;
		justify-content: space-between;
		padding: 20rpx;
		margin: 0rpx 20rpx;
		box-shadow: 0rpx 2rpx 10rpx 0rpx #F0F0F0;
		border-radius: 10rpx;
	}
	.advance view{
		display: flex;
		align-items: center;
		text-align: center;
		width: 200rpx;
		height: 150rpx;
		color: white;
		font-size: 26rpx;
		padding: 20rpx;
		box-sizing: border-box;
		border-radius: 8%;
		box-shadow: 0rpx 10rpx 10rpx 0rpx #F0F0F0;
	}
	.advance view:nth-child(1){
		background-image: linear-gradient(110deg,rgb(81, 142, 212),rgb(4, 89, 248));
	}
	.advance view:nth-child(2){
		background-image: linear-gradient(rgb(255, 72, 0),rgb(230, 104, 46));
	}
	.advance view:nth-child(3){
		background-image: linear-gradient(rgb(150, 4, 247),rgb(144, 65, 235));
	}
	.hot_free{
		margin:40rpx 0rpx 20rpx 0rpx;
		padding: 0rpx 20rpx;
		display: flex;
		align-items: center;
	}
	.hot_free text:nth-child(1){
		font-size: 35rpx;
		font-weight: 700;
		text-align: left;
	}
	.hot_free text:nth-child(2){
		margin-left: 40rpx;
		font-size: 25rpx;
		color: #808080;
	}
	.free_curriculum{
		padding: 20rpx;
		margin:30rpx 30rpx 0rpx 20rpx;
		box-shadow: 0rpx 5rpx 10rpx 0rpx #F0F0F0;
		border-radius: 10rpx;
	}
	.free_curriculum image{
		width: 180rpx;
		height: 180rpx;
		float: left;
		margin-right: 20rpx;
		box-shadow: 0rpx 0rpx 5rpx 5rpx #dddddd;
		border-radius: 10rpx;
	}
	.free_curriculum view:nth-of-type(1){
		font-weight: 700;
		font-size: 30rpx;
	}
	.free_curriculum view:nth-of-type(2),
	.free_curriculum view:nth-of-type(3){
		color: #808080;
		font-size: 25rpx;
		margin-top: 20rpx;
	}
	.free_curriculum .icon text{
		margin: 0rpx 5rpx 0rpx 10rpx;
	}
	.pictrue{
		margin-top: 20rpx;
	}
	.pictrue swiper-item{
		width: 90%;
		height: 90%;
		display: flex;
		justify-content: center;
	}
	.pictrue image{
		width: 90%;
		height: 90%;
		box-shadow: 0rpx 20rpx 10rpx 0rpx #c7c7c7;
		border-radius: 15rpx;
	}
	input{
		background-color: #ebebeb;
		height: 70rpx;
		padding-left: 20rpx;
		margin: 0rpx 30rpx;
		border-radius: 10rpx;
		margin-top: 10rpx;
	}
	input[placeholder]{
		font-size: 28rpx;
	}
</style>
<template>
	<view class="container">
		<input type="text" placeholder="文章,视频,内容" value="" />
		<view class="title">
			<view :class="{active:index==current}" @click="choice(index)" v-for="(item,index) in title" :key="index">{{item}}</view>
		</view>
		<swiper :indicator-active-color="indicator_active_color" :circular="circular" :interval="interval" :autoplay="autoplay" :indicator-dots="indicator_dots" class="pictrue">
			<swiper-item ><image src="../../static/1.jpg" mode=""></image></swiper-item>
			<swiper-item ><image src="../../static/2.jpg" mode=""></image></swiper-item>
			<swiper-item ><image src="../../static/3.jpg" mode=""></image></swiper-item>
		</swiper>
		<view class="get_job">
			<text>零基础就业</text>
			<text>从入门到精通</text>
		</view>
		<view class="technology">
			<view class="java">java</view>
			<view class="html">html</view>
			<view class="css">css</view>
			<view class="javascipt">javascipt</view>
		</view>
		<view class="job_market">
			<text>职场进阶</text>
			<text>1年以上开发经验系成长</text>
		</view>
		<view class="advance">
			<view>java全栈从后端走向全栈</view>
			<view>大前端前端高级进阶</view>
			<view>java架构师专家系统养成</view>
		</view>
		<view class="hot_free">
			<text>热门免费</text>
			<text>0门槛开启你的高薪之路</text>
		</view>
		<view class="free_curriculum" @click="to_video">
			<image src="../../static/python.jpg" mode=""></image>
			<view class="">初识Phthon</view>
			<view class="icon">入门  <text class="icon-renwu"></text>213241 21321人评价</view>
			<view class="">免费</view>
		</view>
		<view class="free_curriculum">
			<image src="../../static/c.jpg" mode=""></image>
			<view class="">初识Phthon</view>
			<view class="icon">入门  <text class="icon-renwu"></text>213241 21321人评价</view>
			<view class="">免费</view>
		</view>
		<view class="free_curriculum">
			<image src="../../static/html.jpg" mode=""></image>
			<view class="">初识Phthon</view>
			<view class="icon">入门  <text class="icon-renwu"></text>213241 21321人评价</view>
			<view class="">免费</view>
		</view>
		<view class="free_curriculum">
			<image src="../../static/java.jpg" mode=""></image>
			<view class="">初识Phthon</view>
			<view class="icon">入门  <text class="icon-renwu"></text>213241 21321人评价</view>
			<view class="">免费</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				title:["推荐","免费课","实战课","就业班","专栏"],
				index:0,
				current:0,
				autoplay:true,
				indicator_dots:true,
				interval:3000,
				circular:true,
				indicator_active_color:"#353535"
			}
		},
		methods:{
			choice(index){
				this.current=index,
				this.index=index
			},
			to_video(){
				uni.navigateTo({
					url:"video/video",
					fail(res) {
						console.log(res)
					}
				})
			}
		}
	}
</script>

