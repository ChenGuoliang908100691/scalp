<template>
	<view class="index">
		<view class="head">
			<view class="jiu">
				<view class="jiu_01">					
					<navigator url="/pages/detail/detail">
						<view><img src="../../imgs/2.png" /></view>
						<view>我的佣金</view>
					</navigator>
				</view>
				<view class="jiu_01 ">
					<navigator url="/pages/detail/detail"> 
						<view><img src="../../imgs/3.png" /></view>
						<view>我的本金</view>
					</navigator>
				</view>
			</view>
		</view>
		
		<uni-notice-bar scrollable="true" single="true" showIcon="true" text="这里是公告栏 这里是公告栏 这里是公告栏 这里是公告栏 这里是公告栏 这里是公告栏"></uni-notice-bar>
		
		<view class="shuju">
			<view class="shuju_01">
					<view>今日预估收益</view>
					<view class="shuju_01_s">¥0</view>
			</view>
			<view class="shuju_01 no">
				<view>待完成总收益</view> 
				 <view class="shuju_01_s">¥0</view>
			</view>
			
			<view class="shuju_01">
				<view>未返本金</view>
				<view class="shuju_01_s">¥0</view>
			</view>
			<view class="shuju_01 no">
				<view>总推广奖励金</view>
				<view class="shuju_01_s">¥0</view>
			</view>
			<view class="shuju_01">
				<view>今日推广奖励</view>
				<view class="shuju_01_s">¥0</view>
			</view>
		</view>
		<view class="more">
			<view class='mo'>
				<view class='mo_01'>客服QQ:76789676</view>
				<view class='mo_02'>工作时间：9:00-20:00<uni-icon type="arrowright" size="15" color="#D6D6D6"></uni-icon>
				</view>
			</view>
		</view>
		<view class="more">
			<view class='mo'>
				<view class='mo_01'>客服微信:78978</view>
				<view class='mo_02'>工作时间：9:00-20:00<uni-icon type="arrowright" size="15" color="#D6D6D6"></uni-icon>
				</view>
			</view>
		</view>
		
		<view class="BH"></view>
		
		<view class="more">
			<view class='mo' style="border: none;">
				<view class='mo_01'>分享赚收益</view>
				<view class='mo_02'></view>
			</view>
		</view>

		<view class="icon">
			<view class="ico" v-for="item of list"><navigator :url="item.url">
				<view class="tubiao">
					<img class="img" :src="item.img"></img>
				</view>
				<view class="tt">
					<view class="text">{{item.title}}</view>
				</view></navigator>
			</view>
		</view>
		<!-- <tab-bar></tab-bar> -->
	</view>
</template>

<script>
	export default {
		components: {
			
		},
		data() {
			return {
				tancl: false,
				list: [{
						title: '分享海报',
						img: require("@/imgs/mp.png"),
						url:"/pages/user/spread/spread"
					},
					{
						title: '分享链接',
						img: require("@/imgs/q.png"),
						url:"/pages/generalize/generalize"
					}
				]
			}
		},
		onLoad() {
			this.getInformation()
		},
		onShow() {  
			
		},
		methods: {
			//扫码
			shao(){
				uni.scanCode({
					onlyFromCamera: true,
					success: function (res) {
						uni.navigateTo({
							url:'pages/edit/yanzheng/yanzheng?code='+res.result
						})
					}
				});
			},
			getInformation(){//获取首页用户信息
				this.$api.http.post('',{},'')
				.then(res =>{
					console.log(res)
				});
			}
		}
	}
</script>

<style lang="scss">
	.index {
		background:#ffffff;
		padding-bottom: 80px;
		.H50{
			height:50px;
		}
		.BH {
			background-color: #F1F1F1;
			height: 5px;
		}
		.head {
			background:  linear-gradient(to bottom, #52c693, #27a26c);
			text-align: center;
			padding: 5px 0 10px;
			color: #fff;
			font-size: 14px;
		}

		.jiu {
			padding: 10px;
			display: flex;
			flex-wrap: wrap;
			color: #fff;
		}

		.jiu_01 {
			width: 50%;
			text-align: center;
			padding: 15px 10px 15px;
			box-sizing: border-box;
			font-size: 12px;
		}

		.jiu_01 img {
			width: 32px;
			height: 32px;
			margin-bottom: 10px;
		}

		.mo {
			padding: 10px;
			display: flex;
			justify-content: space-between;
			border-bottom: 1px solid #f0f0f0;
			line-height: 20px;
		}

		.mo_01 {
			padding-left: 10px;
			box-sizing: border-box;
			width: 50%;
			height: 20px;
			overflow: hidden;
			font-size: 12px;
			font-weight: bold;
		}

		.mo_01 span {
			color: #8E8E8E;
			font-weight: 100;
			font-size: 12px;
			padding-left: 10px;
		}

		.mo_02 {
			width: 50%;
			font-size: 12px;
			color: #D6D6D6;
		}

		.shuju {
			display: flex;
			flex-wrap: wrap;
		}

		.shuju_01 {
			width: 33.3%;
			text-align: center;
			padding: 18px 10px;
			box-sizing: border-box;
			font-size: 14px;
			line-height: 20px;
			font-size: 14px;
		}

		.shuju_01_s {
			color: #EB511B;
			font-weight: 600;
			font-size: 16px;
		}

		.list_01 {
			padding: 15px 10px 8px;
			border-bottom: 1px solid #F4F4F4;
			font-size: 12px;
		}
	}
	.icon {
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		margin-left: 3%;
		margin-right: 3%;
	
		.ico {
			border-radius: 10px;
			border: 1px solid #C0C0C0;
			width: 49%;
			height: 100px;
			margin-top: 10px;
			display: flex;
			border: none;
			font-size: 15px;
			flex-direction: column;
			background-color: #FFFFFF;
	
			.img {
				width: 32px;
				height: 32px;
			}
	
			.tubiao {
				margin-top: 20px;
				text-align: center;
			}
	
			.text {
				color: #8F8F94;padding-top: 5px;
				text-align: center;
				
			}
		}
	}
</style>
