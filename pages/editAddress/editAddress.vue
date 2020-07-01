<template>
	<view class="modificationAddress">
		<view class="tjsp">
			<navigator url="">
				<view class="flex flex-direction">
					<button class="cu-btn margin-tb-sm lg">修改地址</button>
				</view>
			</navigator>
		</view>
		<!-- 一般用法 -->
		<uni-countdown :hour="1" :minute="12" :second="40"></uni-countdown>
		
		<!-- 不显示天数 -->
		<uni-countdown color="#FFFFFF" background-color="#00B26A" border-color="#00B26A" :show-day="false" :hour="12" :minute="12" :second="12"></uni-countdown>
		
		<!-- 修改颜色 -->
		<uni-countdown color="#FFFFFF" background-color="#00B26A" border-color="#00B26A" :hour="2" :minute="30" :second="0"></uni-countdown>
	</view>
</template>

<script>
	import uniCountdown from '@/components/uni-countdown/uni-countdown.vue'
	export default {
		components: {
		  uniCountdown
		},
		data() {
			return {
				
			}
		},
		onLoad() {
			
		},
		methods: {
			
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
