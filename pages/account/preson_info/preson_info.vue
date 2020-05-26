 <style>
	.container{
		height: 100vh;
		background-color: #F8F8F8;
		padding: 0rpx 20rpx;
	}
	.title{
		position: relative;
		height: 40%;
	}
	.backgroud{
		height: 100%;
		text-align: center;
	}
	.backgroud image{
		height: 100%;
		width: 100%;
		filter: blur(1px);
	} 
	.head_portrait{
		text-align: center;
		width: 180rpx;
		height: 180rpx;
		border-radius: 50%;
		position: absolute;
		color: white;
		bottom: -15%;
		/* 计算属性不支持rpx，1px=2rpx */
		left: calc(50% - 45px);
	} 
	.head_portrait image{
		width: 180rpx;
		height: 180rpx;
		border-radius: 50%;
		box-shadow: 2rpx 5rpx 10rpx 0rpx #1b1b1b;
	}
	.content{
		height: 30%;
		background-color: #49d883;
		display: flex;
		justify-content: space-between;
	}
	.left,
	.right{
		width: 290rpx;
		display: flex;
		flex-wrap: wrap;
	}
	.left view,
	.right view{
		width: 49%;
		hiegh:49%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		color: #ffffff;
	} 
 	.info_item:nth-of-type(1),
	.info_item:nth-of-type(2){
		border-bottom: 1rpx solid #CCCCCC;
	}
	.info_item:nth-of-type(2n){
		border-left: 1rpx solid #CCCCCC;
	}
	.info_item .icon-nicheng{
		color: #8b1a06;
		font-size: 57rpx;
	}
	.info_item .icon-icon-1{
		color: #ca0000;
		font-size: 57rpx;
	}
	.info_item .icon-nianling{
		color: #068b2c;
		font-size: 57rpx;
	}
	.info_item .icon-nianling{
		color: #0f3f8b;
		font-size: 57rpx;
	}
	.info_item .icon-dianhua{
		color: #8b8314;
		font-size: 57rpx;
	}
</style>

<template>
	<view class="container">
		<view class="title">
			<view class="backgroud">
				<image src="../../../static/dog.png" mode="aspectFill"></image>
			</view>
			<view class="head_portrait">
				<image src="../../../static/dog.png" mode="aspectFill"></image>
				<view class="nickname">昵称</view>
			</view>
		</view>
		<view class="content">
			<view class="left">
				<view class="info_item">
					<view class="icon-nicheng"></view>
					<text>昵称</text>
				</view>
				<view class="info_item">
					<view class="icon-icon-1"></view>
					<text>性别</text>
				</view>
				<view class="info_item">
					<view class="icon-nianling"></view>
					<text>年龄</text>
				</view>
				<view class="info_item">
					<view class="icon-dianhua"></view>
					<text>电话</text>
				</view>
			</view>
			<view class="right">
				<view class="info_item">
					<view class="icon">图标</view>
					<text>电话</text>
				</view>
				<view class="info_item">
					<view class="icon">图标</view>
					<text>电话</text>
				</view>
				<view class="info_item">
					<view class="icon">图标</view>
					<text>电话</text>
				</view>
				<view class="info_item">
					<view class="icon">图标</view>
					<text>电话</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
</script>


