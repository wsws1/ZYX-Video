<style>
	.container{
		background-color: #F8F8F8;
		padding: 0rpx 20rpx;
		height: 100vh;
	}
	.title{
		display: flex;
		align-items: center;
		background-color: white;
		padding: 30rpx;
	}
	.title image{
		height: 90rpx;
		width: 90rpx;
		border-radius: 45rpx;
		border: 1px solid #CCCCCC;
		margin-right: 20rpx;
	}
	.item_list{
		margin-top: 10rpx;
	}
	.item{
		display: flex;
		justify-content: space-between;
		height: 89rpx;
		line-height: 89rpx;
		font-size: 30rpx;
		font-weight: 700;
		background-color: white;
		padding: 0rpx 20rpx;
		margin-top: 20rpx;
		border-radius:20rpx;
	}
	.wrap{
		display: flex;
	}
	.wrap text:nth-of-type(1){
		font-size: 40rpx;
		margin-right: 20rpx;
	}
	.nickname{
		margin-right: 19rpx;
	}
	.info{
		line-height: 46rpx;
		font-size: 26rpx;
	}
	.icon{
		 margin-left:auto;
		 width: 150rpx;
		 height: 60rpx;
		 text-align: center;
		 line-height: 60rpx;
		 color: #555555;
		 border: 1px solid #555555;
		 font-size: 26rpx;
		 border-radius: 50rpx;
	}

</style>

<template>
	<view class="container">
		<view @click="login" class="title">
			<image :src="avatar"></image>
			<view class="info">
				<text class="nickname">昵称：{{nickname}}</text>
				<text v-show="!gender==''"  :class="[gender==1?'icon-nv':'icon-nv1']"></text>
				<view>城市：{{city}}</view>
			</view>
			<view class="icon">登录/注册</view>
		</view>
		<view class="item_list">
			<view class="item">
				<view class="wrap">
					<text class="icon-icon-"></text>
					<text>我的订单</text>
				</view>
				<text class="icon-arrow-down"></text>
			</view>
			<view class="item">
				<view class="wrap">
					<text class="icon-cart1"></text>
					<text>我的购物车</text>
				</view>
				<text class="icon-arrow-down"></text>
			</view>
			<view class="item">
				<view class="wrap">
					<text class="icon-yue"></text>
					<text>我的余额</text>
				</view>
				<text class="icon-arrow-down"></text>
			</view>
			<view class="item">
				<view class="wrap">
					<text class="icon-youhuijuan"></text>
					<text>我的优惠卷</text>
				</view>
				<text class="icon-arrow-down"></text>
			</view>
			<view class="item">
				<view class="wrap">
					<text class="icon-yijianfankui1"></text>
					<text>帮助和反馈</text>
				</view>
				<text class="icon-arrow-down"></text>
			</view>
			<view class="item">
				<view class="wrap">
					<text class="icon-shezhi"></text>
					<text>设置</text>
				</view>
				<text class="icon-arrow-down"></text>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				nickname:"",
				gender:"",
				avatar:"",
				city:""
			}
		},
		onLoad(res) {
			console.log(res),
			this.avatar=res.avatar,
			this.gender=res.gender,
			this.nickname=res.nickname,
			this.city=res.city
		},
		methods:{
			login(){
				uni.navigateTo({
					url:"../register/register"
				})
			}
		}
	}
</script>
