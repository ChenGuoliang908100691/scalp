<template>
	<view class="reseller">
		<view class="top">
			<view class="top_left">
				<view class="box">
					<image src="../../../imgs/head.jpg" style="width: 80px; height: 80px;border-radius: 50%;" mode=""></image>
				</view>
			</view>
			<view class="top_content">
				<view class="num">
					<view><image src="../../../imgs/win.png" style="width: 15px; height: 15px;margin-right: 5px;" mode=""></image>黄金会员</view>
				</view>
				<view class="num">
					<view>ID:8952</view>
				</view>
				<view class="num">
					<view>用户名:陈大锤</view>
				</view>
				<view class="num">
					<view>积分:9999</view>
				</view>
				
			</view>
			<view class="top_right">
				<view class="num">
					<image src="../../../imgs/mp.png" style="width: 50px; height: 50px;background-color: #fff;" mode=""></image>
				</view>
			</view>
			<view class="top_setting">
				<view class="num">
					<image src="../../../imgs/4.png" style="width: 30px; height: 30px;" mode=""></image>
				</view>
			</view>
			<view class="tixian" @click="jump_question">
				<view class="btn" style="font-size: 16px;">？有问题请点我</view>
			</view>
		</view>
		<view class="BH"></view>
		<view class="six">
			<view class="jiu_01">
				<navigator url="/pages/order/order">
					<view><img src="../../../imgs/8.png" /></view>
					<view>全部任务</view>
				</navigator>
			</view>
			<view class="jiu_01">
				<navigator url="/pages/detail/detail">
					<view><img src="../../../imgs/yhq.png" /></view>
					<view>我要提现</view>
				</navigator>
			</view>
			<view class="jiu_01">
				<navigator url="/pages/binding/binding">
					<view><img src="../../../imgs/yhq.png" /></view>
					<view>绑定账号</view>
				</navigator>
			</view>
			<view class="jiu_01">
				<navigator url="/pages/edit/shop/shop">
					<view><img src="../../../imgs/6.png" /></view>
					<view>门店编辑</view>
				</navigator>
			</view>
			<view class="jiu_01">
				<navigator url="/pages/user/tongji/tongji"> 
					<view><img src="../../../imgs/date.png" /></view>
					<view>经营数据</view>
				</navigator>
			</view>
			<view class="jiu_01 ">
				<navigator url="/pages/regulation/regulation">
					<view><img src="../../../imgs/people.png" /></view>
					<view>账号完成率</view>
				</navigator>
			</view> 
			<view class="jiu_01">
				<navigator url="/pages/user/sort/sort">
					<view><img src="../../../imgs/5.png" /></view>
					<view>意见反馈</view>
				</navigator>
			</view>
			<view class="jiu_01">
				<navigator url="/pages/edit/shop/shop">
					<view><img src="../../../imgs/5.png" /></view>
					<view>版本信息</view>
				</navigator>
			</view>
		</view>
		<view class="BH"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		onShow() {
			
		},
		methods:{
			jump_question(){
				uni.navigateTo({
					url: '/pages/question/question',
				});
			},
			todata(){
				this.$router.push({path:'/pages/user/tongji/tongji'})
			},
		},
		onPullDownRefresh() {
			setTimeout(function() {
				uni.stopPullDownRefresh();
			}, 2000);
		}
	}
</script>

<style lang="less">
	page {
		background-color: #ffffff;
	}
	.BH {
		background-color: #F1F1F1;
		height: 5px;
	}
	.reseller {
		background-color: #ffffff;
		min-height:100vh;
		font-size:14px;
		padding-bottom: 80px;
		.top {
			color: #FFFFFF;
			display: flex;
			position: relative;
			width: 100%;
			height: 250px;
			background-color: #DD524D;
			background: linear-gradient(top, #4EC28E, #1C9C63);
			.top_left{
				padding-top: 18%;
				padding-left: 5%;
				flex: 1;
			}
			.top_content{
				padding-top: 17%;
				padding-left: 5%;
				flex: 5;
			}
			.top_right{
				margin-top: 22%;
				flex: 2;
			}
			.top_setting{
				padding-top: 2%;
				flex: 1;
			}
			.num {
				font-size: 14px;line-height: 25px;
			}
			
		}

		.tixian {
			display: flex;
			justify-content: center;
			background-color: #F5F5F5;
			width: 55%;
			height: 60px;
			border-radius: 60px;
			position: absolute;
			bottom: -30px;
			left: 23%;

			.btn {
				margin-top: 10px;
				text-align: center;
				width: 85%;
				background:  linear-gradient(to bottom, #52c693, #27a26c);
				height: 40px;
				border: none;
				border-radius: 50px;
				line-height: 40px;
				color: #FFFFFF;
			}


		}

		.six {
			padding: 50px 0;
			display: flex;
			flex-wrap: wrap;
		}
		.jiu_01 {
			width: 33.3%;
			text-align: center;
			padding: 15px;
			box-sizing: border-box;
			font-size: 12px;
		}
		.jiu_01 img {
			width: 30px;
			height: 30px;
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
	}
</style>
