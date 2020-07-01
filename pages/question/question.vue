<template>
	<view class="kedetail">
		<view class="head">
			<view class="head_l">
				
			</view>
			<view class="head_r">
				
			</view>
		</view>
		<view class="BH6"></view>
		<view class="jytj">
			<view class="jytj_tit">问题解决</view>
			<view class="con">
				<view class="con_01">
					<view class="con_01_1">账号管理</view>
					<view class="con_01_2">0</view>
				</view>
				<view class="con_01">
					<view class="con_01_1">任务操作</view>
					<view class="con_01_2">0</view>
				</view>
				<view class="con_01">
					<view class="con_01_1">返款问题</view>
					<view class="con_01_2">0</view>
				</view>
				<view class="con_01">
					<view class="con_01_1">其他问题</view>
					<view class="con_01_2">0</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import uniIcon from "@/components/uni/uni-icon/uni-icon.vue"  
	export default {
		data() {
			return {
				sex:false
			};
		},
		components: {
			uniIcon 
		}
	}
</script>

<style lang="scss">
.kedetail{
	.head{
		display: flex;
		margin: 10px;
		padding:10px 5px;
		.head_l{
			
		}
		.head_r{
			
		}
	}
	.BH6{
		height: 6px;
		background-color: #FAFAFA;
		}
	.jytj{
		padding: 30px 10px 15px;
		.jytj_tit{
			font-size: 18px;
			font-weight: 600;
			padding-bottom: 20px;
			}
		.con{
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;
			.con_01{
				width: 48%;
				padding: 10px 0 20px;
				box-sizing: border-box;
				.con_01_1{
					color: #A4A5A7;
					}
				.con_01_2{
					font-size: 18px;
					font-weight: 600;
					padding-top: 20px;
					line-height: 20px;
					span{
						padding-left: 10px;
						}
				}
			}
		}
	}
}
</style>
