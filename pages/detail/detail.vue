<template>
	<view class="detail">
		<view style="display: flex;justify-content: space-between;margin-bottom: 10px;">
			<view class="money">总佣金：￥100.00</view>
			<view class="head_btn" @click="jump_cash">去提现</view>
		</view>
		<view class="commission">
			<view class="commissionBox1">
				<view class="">我的佣金</view>
				<view class="">￥100.00</view>
			</view>
			<view class="BH"></view>
			<view class="commissionBox2">
				<view class="">我的本金</view>
				<view class="">￥999.00</view>
			</view>
		</view>
		<view class="record">
			<block v-for="(item,index) of list" :key="index">
				<li class="recordBox" @click="jump(item.id)">
					<view class="recordBox_l">
						<span>代理提成-{{item.card.bank_num.substr(item.card.bank_num.length-4)}}</span><br/>{{item.create_time}}
					</view>
					<view class="recordBox_2">
						+{{item.money}}<br/>
						<span v-if="item.status==0">提现中</span>
						<span v-if="item.status==1">已完成</span>
					</view>
				</li>
			</block>
		</view>
	</view>
</template>

<script>
	export default {
		components: {
			
		},
		data() {
			return {
				list:[],
				num:0,
			};
		},
		onLoad() {  
			this._load()
		},
		methods:{
			_load(){ 
				this.list=this.$api.json.get_tx_log
			},
			jump_cash(){
				uni.navigateTo({
					url:'/pages/user/fenxiao/tixian/tixian'
				})
			},
			jump(id){
				uni.navigateTo({
					url:'/pages/user/fenxiao/success/success?id='+id
				})
			},
			change(e){
				this.num=e 
			}
		}
	}
</script>

<style lang="less">
.detail{
	.BH {
		background-color: #F1F1F1;
		height: 5px;
	}
	.money{
		margin:10px 20px 0;
		padding: 0px 15px;
		line-height: 25px;
		color: #00B26A;
	}
	.head_btn{
		margin:10px 20px 0;
		border: 1px solid #F2F2F2;
		padding: 0px 15px;
		line-height: 25px;
	}
	.commission{
			.commissionBox1{
				height:100px;
				background:  linear-gradient(to bottom, #52c693, #27a26c);
				display: flex;
				view{
					flex: 1;
					line-height: 100px;
					text-align: center;
					font-size: 20px;
					color: #fff;
				}
			}
			.commissionBox2{
				height:100px;
				background:  linear-gradient(to bottom, #52c693, #27a26c);
				display: flex;
				view{
					flex: 1;
					line-height: 100px;
					text-align: center;
					font-size: 20px;
					color: #fff;
				}
			}
		}
	// .record li:nth-of-type(odd){
	// 	background-color: #EEEEEE;
	// } 
	// .record li:nth-of-type(even){
	// 	background-color: #fff;
	// } 
	.recordBox{
		display: flex;
		justify-content: space-between;
		padding: 8px;
		line-height: 25px;
		font-size: 14px;
		border-bottom:1px solid #F2F2F2
	}
	.recordBox_l{
		color: #9A9A9A;
	}
	.recordBox_l span{
		font-size: 14px;
		color: #000;
	}
	.recordBox_2{
		color: #E1461D;
	}
	.recordBox_2 span{
		color: #9A9A9A;
	}
}
</style>
