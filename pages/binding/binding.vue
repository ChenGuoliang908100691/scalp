<template>
	<view class="binding">
		<view class="title padding">账户信息（银行卡和账户信息一致）*必填</view>
		<view class="message padding-sm" @click="messageBinding">
			<view class="messageBox">
				<view class="messageBox_l text-bold">账户信息</view>
				<view class="messageBox_m text-gray"></view>
				<view class="messageBox_r">已绑定<text class="lg cuIcon-right text-gray" ></text></view>
			</view>
		</view>
		<view class="message padding-sm" @click="qqBinding">
			<view class="messageBox">
				<view class="messageBox_l text-bold">QQ号码</view>
				<view class="messageBox_m text-gray"></view>
				<view class="messageBox_r">已绑定1234<text class="lg cuIcon-right text-gray" ></text></view>
			</view>
		</view>
		
		<view class="BH"></view>
		
		<view class="title padding">账户信息（任意绑定一个号码并且通过审核）</view>
		<view class="message padding-sm" @click="taobaoBinding">
			<view class="messageBox">
				<view class="messageBox_l text-bold">淘宝</view>
				<view class="messageBox_m text-gray">已绑定</view>
				<view class="messageBox_r">1234<text class="lg cuIcon-right text-gray" ></text></view>
			</view>
		</view>
		<view class="message padding-sm" @click="jingdongBinding">
			<view class="messageBox">
				<view class="messageBox_l text-bold">京东</view>
				<view class="messageBox_m text-gray">未绑定</view>
				<view class="messageBox_r">{{}}<text class="lg cuIcon-right text-gray" ></text></view>
			</view>
		</view>
		<view class="message padding-sm" @click="pinduoduoBinding">
			<view class="messageBox">
				<view class="messageBox_l text-bold">拼多多</view>
				<view class="messageBox_m text-gray">未绑定</view>
				<view class="messageBox_r">{{}}<text class="lg cuIcon-right text-gray" ></text></view>
			</view>
		</view>
		
		<view class="BH"></view>
		
		<view class="title padding">修改收货信息</view>
		<view class="message padding-sm" @click="modificationAddress">
			<view class="messageBox">
				<view class="messageBox_l text-bold">修改收货信息</view>
				<view class="messageBox_m text-gray"></view>
				<view class="messageBox_r"><text class="lg cuIcon-right text-gray" ></text></view>
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
			messageBinding(){//	账户信息绑定
				uni.navigateTo({
					url:'../accountMessage/accountMessage'
				})
			},
			qqBinding(){//qq绑定
				uni.navigateTo({
					url:'../qqBinding/qqBinding'
				})
			},
			taobaoBinding(){//淘宝绑定
				uni.navigateTo({
					url:'../taobaoBinding/taobaoBinding'
				})
			},
			jingdongBinding(){//京东囊定
				uni.navigateTo({
					url:'../jingdongBinding/jingdongBinding'
				})
			},
			pinduoduoBinding(){//拼多多绑定
				uni.navigateTo({
					url:'../pinduoduoBinding/pinduoduoBinding'
				})
			},
			modificationAddress(){//修改地址
				uni.navigateTo({
					url:'../modificationAddress/modificationAddress'
				})
			}
			
		}
	}
</script>

<style lang="less">
	.binding{
		.BH {
			background-color: #F1F1F1;
			height: 10px;
		}
		.title{
			text-align: center;
			font-size: 16px;
			background:  linear-gradient(to bottom, #52c693, #27a26c);
			color: #ffffff;
		}
		.message{
			font-size: 15px;
			background-color: #ffffff;
			.messageBox{
				display: flex;
				padding: 15px 0;
				.messageBox_l{
					flex: 1;
				}
				.messageBox_m{
					flex: 1;
				}
				.messageBox_r{
					flex: 1;
					text-align: right;
				}
			}
		}
	}
	
</style>
