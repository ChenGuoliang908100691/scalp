<template>
	<view class="product">
		<view class="top">
			<view class="title" >
				<view class="text" @click="toRegulation">设置好平台模式,可组合多个平台同时接单。</view>
				<view class="regulation" @click="toRegulation" style="margin-top:10px;width:20px;height:20px;border:1px solid #fff;border-radius:50%;text-align:center;line-height:20px;">?</view>
				<view class="binding" @click="toBinding">绑定账号</view>
			</view>
		</view>
		<view class="">
			<view class="cu-form-group ">
				<view class="title"><image src="../../imgs/淘宝.png" style="width: 30px;height:30px;" mode=""></image></view>
				<view class="title">以绑定</view>
				<view class="title">今日垫付：1/2</view>
				<view class="title" >
					<switch @change=""></switch> 
				</view>
			</view>
			<view class="cu-form-group ">
				<view class="title"><image src="../../imgs/京东.png" style="width: 28px;height:28px;" mode=""></image></view>
				<view class="title">以绑定</view>
				<view class="title">今日垫付：1/2</view>
				<view class="title" >
					<switch @change=""></switch> 
				</view>
			</view>
			<view class="cu-form-group ">
				<view class="title"><image src="../../imgs/拼多多.png" style="width: 25px;height:25px;" mode=""></image></view>
				<view class="title">以绑定</view>
				<view class="title">今日垫付：1/2</view>
				<view class="title" >
					<switch @change=""></switch> 
				</view>
			</view>
		</view>
		<view class="p_btn">
			<button class="pro_btn" type="button" @click="orderReceiving()">接单</button>
			<view class="time">00:0{{count}}</view>
			<view class="title">浏览单可无限接,每日接单量上限由系统风控自动判定无需咨询客服原因,回复结果都一样.</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				count:0,
				forbid:true
			};
		},
		components: {
			
		},
		computed: {
		
		},
		onLoad(options) {
			
		},
		onShow() {
			
		},
		methods: {
			orderReceiving(){//接单
				if(this.forbid==true){
					this.forbid = false
					let that = this
					let num = 0
					let time = setInterval(function(){
						num++;
						if(num>=10){
							clearInterval(time)
							that.$api.http.post('/index.php/User/Task/ceshi',{userId:12774},'post')
							.then(res =>{
								console.log(res)//请求成功返回的数据
							});
							uni.showModal({
							    title: '任务名称',
							    content: '佣金：￥8.00',
							    success: function (res) {
							        if (res.confirm) {
							            console.log('用户点击确定');
							        } else if (res.cancel) {
							            console.log('用户点击取消');
							        }
							    }
							});
						}
						that.count = num
						if(num>=10){
							that.count = 0
							that.forbid = true
						}
						console.log(that.count)
					},1000)
				}
				
			},
			toRegulation(){//跳转到规则页面
				uni.navigateTo({
					url:'../regulation/regulation'
				})
			},
			toBinding(){//跳转到绑定页面
				uni.navigateTo({
					url:'../binding/binding'
				})
			},
		}
	}
</script>

<style lang="less">
	page {
		background-color: #ffffff;
	}
	.product{
		.top{
			font-size: 10px;
			.title{
				overflow: hidden;
				height:40px;
				line-height:40px;
				background:  linear-gradient(to bottom, #52c693, #27a26c);
				color: #fff;
				padding: 0 10px;
				.text{
					float: left;
				}
				.regulation{
					float: left;
				}
				.binding{
					float: right;
					padding: 0 10px;
					color: #ed1941;
					font-weight: 600;
				}
			}
		}
		.p_btn{
			width:100%;
			text-align: center;
			position: fixed;
			left:0;
			bottom:50px;
			.pro_btn{
				width:60px;
				height:60px;
				background:  linear-gradient(to bottom, #52c693, #27a26c);
				border-radius: 50%;
				line-height:60px;
				text-align: center;
				color: #fff;
				display:block;
				margin-left:auto;
				margin-right:auto;
			}
			.time{
				color:#ff9966;
				padding: 2px 0;
			}
			.title{
				padding: 8px 40px;
				line-height: 15px;
				font-size: 10px;
				color: #999999;
			}
		}
	}
	
	
</style>
