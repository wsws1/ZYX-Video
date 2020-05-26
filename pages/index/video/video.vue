<style>
	.container{
		width: 100vw;
		height: 100vh;
	}
	.video{
		width: 100vw;
		height: 30vh;
	}
	video{
		width: 100vw;
		height: 30vh;
	}
	.tab{
		display: flex;
		justify-content: space-between;
		padding:25rpx 30rpx;
		color: #858487;
		box-shadow: 0rpx 3rpx 8rpx 5rpx #f9f9f9;
		font-size: 30rpx;
	}
	.title{
		padding: 30rpx 0rpx;
		margin: 0rpx 30rpx;
		background-color: white;
		margin-top: 10rpx;
		border-bottom: 1rpx solid #f1f1f1;
		
	}
	.title view:nth-of-type(1){
		font-size: 40rpx;
		font-weight: bold;
		margin-bottom: 20rpx;
	}
	.title view:nth-of-type(2){
		font-size: 28rpx;
		color: #808080;
	}
	.title view:nth-of-type(2) text{
		margin:0rpx 10rpx 0rpx 20rpx;
		display: inline-block;
		margin-top: 10rpx;
	}
	.lessons{
		padding: 30rpx;
	}
	.lessons_title{
		font-size: 33rpx;
		font-weight: 700;
		padding: 20rpx 0rpx;
	}
	.lessons_content{
		font-size: 30rpx;
		color: #444444;
	}
	.lessons_content view{
		padding: 10rpx 0rpx;
	}
	.icon-daima{
		margin: 0rpx 20rpx;
	}
</style>
<template>
	<view class="container">
			<view class="video">
				<video :show-mute-btn="show_mute_btn" :enable-play-gesture="enable_play_gesture" :show-center-play-btn="show_center_play_btn" :page-gesture="page_gesture" src="https://img.cdn.aliyun.dcloud.net.cn/guide/uniapp/%E7%AC%AC1%E8%AE%B2%EF%BC%88uni-app%E4%BA%A7%E5%93%81%E4%BB%8B%E7%BB%8D%EF%BC%89-%20DCloud%E5%AE%98%E6%96%B9%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B@20181126-lite.m4v" controls></video>
			</view>
		<view class="content">
			<view class="tab">
				<text>章节</text>
				<text>详情</text>
				<text>评论</text>
				<text>收藏</text>
				<text>下载</text>
			</view>
			<view class="title">
				<view class="">初识Phthon</view>
				<view class="icon">入门 <text class="iconfont icon-14rentou"></text>213241</view>
			</view>
			<view class="lessons">
				<view class="lessons_item">
					<view class="lessons_title">
						第1章 课程介绍
					</view>
					<view class="lessons_content">
						<text type="" class="icon-daima"></text> 1-1Phython入门课程介绍(04:16)
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第2章 安装Python
					</view>
					<view class="lessons_content">
						<view class=""><text type="" class="icon-daima"></text> 2-1 选择Python版本(00:51)</view>
						<view class=""><text type="" class="icon-daima"></text>  2-2 Windows上安装Python (04:16)</view>
						<view class=""><text type="" class="icon-daima"></text> 2-3 第一个Python程序 (04:16)</view>
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第3章 Python变量和数据类型
					</view>
					<view class="lessons_content">
						<view><text type="" class="icon-daima"></text> 3-1 Python中数据类型 </view>	
						<view><text type="" class="icon-daima"></text> 3-2 Python之print语句 </view>	
						<view><text type="" class="icon-daima"></text> 3-3 Python的注释 </view>	
						<view><text type="" class="icon-daima"></text> 3-4 Python中什么是变量 </view>	
						<view><text type="" class="icon-daima"></text> 3-5 Python中定义字符串 </view>	
						<view><text type="" class="icon-daima"></text> 3-6 Python中raw字符串与多行字符串 </view>	
						<view><text type="" class="icon-daima"></text> 3-7 Python中Unicode字符串 </view>	
						<view><text type="" class="icon-daima"></text> 3-8 Python中整数和浮点数 </view>	
						<view><text type="" class="icon-daima"></text> 3-9 Python中布尔类型 </view>	
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第4章 List和Tuple类型
					</view>
					<view class="lessons_content">
						<view><text type="" class="icon-daima"></text> 4-1 Python创建list</view>	
						<view><text type="" class="icon-daima"></text> 4-2 Python按照索引访问list</view>	
						<view><text type="" class="icon-daima"></text> 4-3 Python之倒序访问list</view>	
						<view><text type="" class="icon-daima"></text> 4-4 Python之添加新元素</view>	
						<view><text type="" class="icon-daima"></text> 4-5 Python从list删除元素</view>	
						<view><text type="" class="icon-daima"></text> 4-6 Python中替换元素</view>	
						<view><text type="" class="icon-daima"></text> 4-7 Python之创建tuple</view>	
						<view><text type="" class="icon-daima"></text> 4-8 Python之创建单元素tuple</view>	
						<view><text type="" class="icon-daima"></text> 4-9 Python之“可变”的tuple</view>	
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第5章 条件判断和循环
					</view>
					<view class="lessons_content">
						<view><text type="" class="icon-daima"></text> 5-1 Python之if语句</view>	
						<view><text type="" class="icon-daima"></text> 5-2 Python之 if-else</view>	
						<view><text type="" class="icon-daima"></text> 5-3 Python之 if-elif-else</view>	
						<view><text type="" class="icon-daima"></text> 5-4 Python之 for循环</view>	
						<view><text type="" class="icon-daima"></text> 5-5 Python之 while循环</view>	
						<view><text type="" class="icon-daima"></text> 5-6 Python之 break退出循环</view>	
						<view><text type="" class="icon-daima"></text> 5-7 Python之 continue继续循环</view>	
						<view><text type="" class="icon-daima"></text> 5-8 Python之 多重循环</view>	
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第6章 Dict和Set类型
					</view>
					<view class="lessons_content">
						<view><text type="" class="icon-daima"></text> 6-1 Python之什么是dict</view>	
						<view><text type="" class="icon-daima"></text> 6-2 Python之访问dict</view>	
						<view><text type="" class="icon-daima"></text> 6-3 Python中dict的特点</view>	
						<view><text type="" class="icon-daima"></text> 6-4 Python更新dict</view>	
						<view><text type="" class="icon-daima"></text> 6-5 Python之 遍历dict</view>	
						<view><text type="" class="icon-daima"></text> 6-6 Python中什么是set</view>	
						<view><text type="" class="icon-daima"></text> 6-7 Python之 访问set</view>	
						<view><text type="" class="icon-daima"></text> 6-8 Python之 set的特点</view>	
						<view><text type="" class="icon-daima"></text> 6-9 Python之 遍历set</view>	
						<view><text type="" class="icon-daima"></text> 6-10 Python之 更新set</view>	
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第7章 函数
					</view>
					<view class="lessons_content">
						<view><text type="" class="icon-daima"></text> 7-1 Python之什么是函数</view>	
						<view><text type="" class="icon-daima"></text> 7-2 Python之调用函数</view>	
						<view><text type="" class="icon-daima"></text> 7-3 Python之编写函数</view>	
						<view><text type="" class="icon-daima"></text> 7-4 Python函数之返回多值</view>	
						<view><text type="" class="icon-daima"></text> 7-5 Python之递归函数</view>	
						<view><text type="" class="icon-daima"></text> 7-6 Python之定义默认参数</view>	
						<view><text type="" class="icon-daima"></text> 7-7 Python之定义可变参数</view>	
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第8章 切片
					</view>
					<view class="lessons_content">
						<view><text type="" class="icon-daima"></text> 8-1 对list进行切片</view>	
						<view><text type="" class="icon-daima"></text> 8-2 倒序切片</view>	
						<view><text type="" class="icon-daima"></text> 8-3 对字符串切片</view>	
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第9章 迭代
					</view>
					<view class="lessons_content">
						<view><text type="" class="icon-daima"></text> 9-1 什么是迭代</view>	
						<view><text type="" class="icon-daima"></text> 9-2 索引迭代</view>	
						<view><text type="" class="icon-daima"></text> 9-3 迭代dict的value</view>	
						<view><text type="" class="icon-daima"></text> 9-4 迭代dict的key和value</view>	
					</view>
				</view>
				<view class="lessons_item">
					<view class="lessons_title">
						第10章 列表生成式
					</view>
					<view class="lessons_content">
						<view><text type="" class="icon-daima"></text> 10-1 生成列表</view>	
						<view><text type="" class="icon-daima"></text> 10-2 复杂表达式</view>	
						<view><text type="" class="icon-daima"></text> 10-3 条件过滤</view>	
						<view><text type="" class="icon-daima"></text> 10-4 多层表达式</view>	
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
    data() {
        return {
           page_gesture:true,
		   show_center_play_btn:false,
		   enable_play_gesture:true,
		   show_mute_btn:true
        }
    },
    methods: {
       
       
       
       
    }
}
</script>
