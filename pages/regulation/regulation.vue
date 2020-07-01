<template>
	<view class="regulation">
		<view class="mess">
			<view class="title">接单规则</view>
			<view class="content">
				平台采用派单机制，用户打开APP，登录平台后，需开启接单模式，选择愿意接单的任务类型等条件，等待系统派单，系统有订单时，会根据如下几个规则综合后选择用户派单：
			</view>
			<view class="list">
				<view class="listBox">
					<view class="mess_02_l">1.开启接单模式的用户</view>
				</view>
				<view class="listBox">
					<view class="mess_02_l">2.符合商家对账号的要求</view>
				</view>
				<view class="listBox">
					<view class="mess_02_l">3.符合平台对时间间隔和订单数量的要求</view>
				</view>
				<view class="listBox">
					<view class="mess_02_l">4.优先给完成率高、被投诉率低、接单量少的用户</view>
				</view>
			</view>
		</view>
		<view class="mess">
			<view class="title">完成率</view>
			<view class="content">
				完成率是指你完成的订单数占所有系统派送给你的订单总数百分比。
			</view>
			<view class="list">
				<view class="listBox">
					<view class="mess_02_l">1.系统派单之后不去操作，造成超时系统自动取消订单</view>
				</view>
				<view class="listBox">
					<view class="mess_02_l">2.用户要求商家取消订单（或商家要求用户取消订单）</view>
				</view>
				<view class="listBox">
					<view class="mess_02_l">3.用户自行取消订单</view>
				</view>
				<view class="listBox">
					<view class="mess_02_l">4.管理员撤销的订单</view>
				</view>
			</view>
			<view class="content">
				维持高完成率可以保持集结号对商家和用户的可靠性，也会增加系统派送订单给你的优先级。
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		components: {
			
		},
		data() {
			
		},
		onLoad() {
			
		},
		onShow() {
			
		},
		methods:{
			
		}
	}
</script>

<style lang="less">
	.regulation{
		.mess{
			background-color: #fff;
			padding: 10px 15px;
			margin-bottom: 10px;
			.title{
				border-left: 3px solid #00B26A;
				padding-left: 10px;
				margin-bottom: 10px;
				font-size: 16px;
				font-weight: 600;
			}
			.content{
				line-height: 20px;
				font-size: 14px;
			}
			.list{
				border-top: 1px solid #D6D6D6;
				padding: 10px;
				font-size: 12px;
				.listBox{
					line-height: 25px;
					color: #D6D6D6;
				}
			}
		}
	}
	
</style>
