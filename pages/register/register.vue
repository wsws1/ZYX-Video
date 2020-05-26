<style>
	.container{
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.container image{
		width: 200rpx;
		height: 200rpx;
		margin-top: 20%;
		border-radius: 50%;
	}
	.phone_number,
	.verification_code{
		width: 560rpx;
		height: 88rpx;
		margin-top: 50rpx;
		background-color: rgb(238, 238, 238);
		padding-left: 30rpx;
		border-radius: 50rpx;
		box-shadow: 2rpx 2rpx 10rpx 0rpx #dfdee3;
	}
	
	.btn{
		margin-top: 50rpx;
		height: 88rpx;
		width: 583rpx;
		border-radius: 50rpx;
		background-color: rgb(5, 187, 29);
		text-align: center;
		line-height: 88rpx;
		color: white;
		box-shadow: 0rpx 5rpx 10rpx #a2a2a2;
	}
	.agree{
		width: 560rpx;
		text-align: center;
		display: flex;
		justify-content: center;
		color: #999999;
		margin-top: 40rpx;
		font-size: 28rpx;
		align-items: center;
	}
	.agree radio{
		transform: scale(.7);
	}
	.agree a{
		color: #858188;
	}
	.verification_code_father{
		position: relative;
	}
	.get_dode{
		position: absolute;
		right: 38rpx;
		bottom: 23rpx;
		color: #808080;
		font-size: 29rpx;
		padding-left: 15rpx;
		height: 44rpx;
		line-height: 50rpx;
		border-left: 2rpx solid #a7a7a7;
		width: 147rpx;
		z-index: 2;
		text-align: center;
	}
	.other_login{
		font-size: 28rpx;
		height: 100rpx;
		line-height: 100rpx;
		margin-top: 50rpx;
		position: relative;
		padding: 0rpx 10rpx;
		color: rgb(126, 126, 126);
	}
	.other_login::after{
		content: "";
		position: absolute;
		height: 2rpx;
		width: 170rpx;
		background-color: #CCCCCC;
		margin-top: 50rpx;
		left: 218rpx;
	}
	.other_login::before{
		content: "";
		position: absolute;
		height: 2rpx;
		width: 170rpx;
		background-color: #CCCCCC;
		margin-top: 50rpx;
		right: 218rpx;
	}
	.icon-weixin{
		font-family: 'iconfont';
		font-size: 88rpx;
		color: #999999;
	}
	.phClass{
		font-size: 28rpx;
	}
	.icon-weixin{
		font-family: 'iconfont';
		font-size: 68rpx;
		color: #444444 !important;
		position: relative;
	}
	button{
		width: 72rpx;
		height: 75rpx;
		position: absolute;
		bottom: 0rpx;
		opacity: 0;
	}
</style>
<template>
	<view class="container">
		<image src="../../static/head_portrait.png" mode=""></image>
		<view>
			<input v-model="phone_number" placeholder-class="phClass" maxlength="14" class="phone_number" type="number"
			 placeholder="请输入手机号" />
		</view>
		<view class="verification_code_father">
			<input v-model="verification_code" placeholder-class="phClass" maxlength="6" class="verification_code" type="number" value="123"
			 placeholder="请输入验证码" />
			<text @click="is_click && get_code()" class="get_dode">{{verify}}</text>
		</view>
		<view @click="login" class="btn">登录</view>
		<view class="agree">
			<radio @click="change" :checked="is_true" />
			同意<a href="">❬❬使用条款和数据隐私政策❭❭</a>
		</view>
		<text class="other_login">其它账号登录</text>
		<view class="icon-weixin">
			<button @getuserinfo="getUserInfo" bind open-type="getUserInfo" withCredentials="true">获取用户信息</button>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				is_true: true,
				phone_number: "",
				//用户输入得验证码
				verification_code: null,
				verify: "获取验证码",
				//验证倒计时
				count_down: 60,
				//存储接收验证码
				verify_code: 123,
				//获取验证码是否禁用
				is_click: true,
				status:""
			}
		},
		onLoad: function() {
			
		},
		methods: {
			change() {
				this.is_true = !this.is_true
			},
			get_code() {
				var phone_reg = /^[1][3,4,5,7,8,9][0-9]{9}$/;
				if (!phone_reg.test(this.phone_number)) {
					uni.showToast({
						"title": "手机号错误，请重新填写",
						"icon": "none"
					});
					return;
				}
				let that = this;
				that.is_click = false;
				var timer = setInterval(function() {
					that.verify = that.count_down-- + " S";
					if (that.count_down < -1) {
						clearInterval(timer);
						that.verify = "获取验证码";
						that.count_down = 60;
						that.is_click = true;
						return;
					}
				}, 1000)
				uni.request({
					url: '',
					method: 'GET',
					data: {},
					success: res => {
						that.verify_code = res;
					},
				});
			},
			login() {
				var that = this;
				var phone_reg = /^[1][3,4,5,7,8,9][0-9]{9}$/;
				if (!phone_reg.test(that.phone_number)) {
					uni.showToast({
						"title": "手机号不正确，请重新输入",
						"icon": "none"
					});
					return;
				};
				if (that.is_true == false) {
					uni.showToast({
						"title": "请同意用户协议",
						"icon": "none"
					});
					return;
				}
				if (that.verification_code == that.verify_code) {
					wx.switchTab({
						url: '/pages/account/account',
						fail(res) {
							console.log(res)
						}
					})
				} else {
					uni.showToast({
						"title": "验证码不正确",
						"icon": "none"
					});
					return;
				};
			},
			getUserInfo(){
				wx.authorize({
					scope:"scope.userInfo",
					complete(e){
						uni.getSetting({
						  success (res) {
							  if(res.authSetting["scope.userInfo"]){
									uni.getUserInfo({
										success(res){
											let nickname=res.userInfo.nickName;
											let gender=res.userInfo.gender;
											let avatar=res.userInfo.avatarUrl;
											let city=res.userInfo.city;
											wx.showLoading({
												title: '登录中...'
											});
											wx.reLaunch({
												"url":"../account/account?nickname="+nickname+"&gender="+gender+"&avatar="+avatar+"&city="+city
											})
										}
									});
							  }else{
								  wx.showToast({
								  	"title":"登录失败，请重新授权",
								  	"icon":"none"
								  })
							  }
						  }
						})
					}
				})
			}
			
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				// uni.login({
				// 	// "provider":"weixin",
				// 	success(res){
				// 		console.log(res)
				// 		uni.getUserInfo({
				// 			success(res) {
				// 				console.log(res)
				// 			}
				// 		})
				// 	}
				// })
				
				
				
				// if(that.static==true)
				// wx.getSetting({
				// 	success(res) {
				// 		that.status=res.authSetting["scope.userInfo"]
				// 		console.log(that.status)
				// 	}
				// })
				// wx.authorize({
				// 	scope: 'scope.record'
				// });
				// wx.getSetting({
				// 	success(res){
				// 		if(!res.authSetting['scope.userInfo']){
				// 			uni.showToast({
				// 				"title":"登录失败",
				// 				"icon":"none"
				// 			})
				// 		}else{
				// 			wx.login({
				// 			success(res){
				// 				wx.request({
				// 					url:"http://192.168.1.3:8085/core/api/sso/getOpenId",
				// 					header:{
				// 						"content-type":"application"
				// 					},
				// 					method:"POST",
				// 					data:{
				// 						"Code":res.code
				// 					},
				// 					success(res){
				// 						that.openid=res.data.result.data.openid,
				// 						wx.request({
				// 							url:"http://192.168.1.3:8072/app/api/account/ucAccount/weChatLogin",
				// 							header:{
				// 								"content-type":"application"
				// 							},
				// 							method:"POST",
				// 							data:{
				// 								OpenId:res.data.result.data.openid
				// 							},
				// 							success(res){
				// 								wx.getUserInfo({
				// 								success(res){
				// 									console.log(res),
				// 									wx.request({
				// 										url:"http://192.168.1.3:8072/app/api/account/ucAccount/saveWechatUserInfo",
				// 										header:{
				// 											"content-type":'application'
				// 										},
				// 										method:"POST",
				// 										data:{
				// 											OpenId:that.openid,
				// 											Telephone:"",
				// 											NickName:res.userInfo.nickName,
				// 											Gender:res.userInfo.gender,
				// 											Brithday:"",
				// 											Avatar:res.userInfo.avatarUrl
				// 										}
				// 									}),
				// 									wx.reLaunch({
				// 										url:"/pages/account/account"
				// 									})
				// 								}
				// 							})
				// 							}
				// 						})
				// 					}
				// 				})
				// 			}
				// 		})

				// 		}
				// 	}
		}
	}
</script>
