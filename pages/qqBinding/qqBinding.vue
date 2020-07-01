<template>
	<view class="qqBinding">
		<view class="BH"></view>
		
		<view class="content">
			<text class="cuIcon-warn text-green"></text>
			<text class="text-gray">为了方便与您联系请务必填写真实的QQ号码</text>
		</view>
		
		<view class="qqInformation">
			<view class="cu-form-group">
				<view class="title">QQ</view>
				<input placeholder="输入QQ号码" name="input"></input>
			</view>
		</view>
		<view class="button">
			<button class="cu-btn lg">提交</button>
		</view>
	</view>
</template>

<script>
	export default{
		components: {
			
		},
		data() {
			return{
				
			}
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
	.qqBinding{
		.BH {
			background-color: #F1F1F1;
			height: 5px;
		}
		.content{
			height:30px;
			line-height: 30px;
			padding: 0 15px;
		}
		.button{
			width: 100%;
			padding: 10px;
			button{
				width: 100%;
				background-color: #00B26A;
				color: #ffffff;
			}
		}
	}
</style>
