<template>
	<view class="modificationAddress">
		<view class="content">
			<view class="cu-form-group" @click="toEditAddress">
				<view class="title">淘宝</view>
				<view class="title">修改地址</view>
			</view>
			<view class="cu-form-group" @click="toEditAddress">
				<view class="title">京东</view>
				<view class="title">修改地址</view>
			</view>
			<view class="cu-form-group" @click="toEditAddress">
				<view class="title">拼多多</view>
				<view class="title">修改地址</view>
			</view>
		</view>

		<view class="tjsp">
			<navigator url="">
				<view class="flex flex-direction">
					<button class="cu-btn margin-tb-sm lg">修改地址</button>
				</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default {
		components: {
			
		},
		data() {
			return {
				
			}
		},
		onLoad() {
			
		},
		methods: {
			toEditAddress(){//跳转到修改页
				uni.navigateTo({
					url:'../editAddress/editAddress'
				})
			}
		}
	}
</script>

<style lang="less">
	.modificationAddress {
			.tjsp {
				padding: 0 10px;
				position: fixed;
				bottom: 0;
				left: 0;
				width: 100%;
				box-sizing: border-box;
				z-index: 99;
				background-color: #fff;
				button {
					background-color: #E5E5E5;
					padding: 10px;
					text-align: center;
					border-radius: 20px;
					background-color: #00B26A;
					color: #fff;
					width: 100%;
				}
			}

	}
</style>
