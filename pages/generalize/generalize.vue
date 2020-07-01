<template>
	<view class="shop">
		<view class="head">
			<view class="head-l">
				<img src="@/imgs/generalize.png"></img>
			</view>
		</view>
		<view class="pingfen">
			<view class="pf">
				<img src="@/imgs/q.png"></img>
			</view>
			<view class="pingfen-r">
				<span>邀请好友:链接邀请好友链接邀请好友链接邀请好友链接邀请好友链接邀请好友链接</span>
			</view>
		</view>
		<view class="copylink">
			<view class="copylink_hade">
				链接如下
			</view>
			<view class="title">
				http://baidu.com
			</view>
			<button type="default">复制邀请链接</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.shop{
	background-color: #fff;
	.head{
		padding: 40px  0;
		display: flex;
		.head-l{
			img{
				width: 100%;
				height: 100%;
				border-radius: 5px;
				}
		}
	}
	.pingfen{
		display: flex;
		justify-content: space-between;
		margin: 5px  10px;
		.pf{
			width:20%;
			height:auto;
			background-color: #fff;
			box-sizing: border-box;
			border-radius: 3px;
			text-align: center;
			img{
				width: 50px;
				height:50px;
				}
		
		}
		.pingfen-r{
			margin-top: 8px;
			width: 80%;
			background-color: #fff;
			box-sizing: border-box;
			span{
				color: #52c693;
				font-size: 12px;
				font-weight: 600;
				}
		}
	}
	.copylink{
		.copylink_hade{
			height:auto;
			font-size: 16px;
			padding: 15px 30px;
			color: #00B26A;
		}
		.title{
			height:auto;
			font-size: 14px;
			padding: 15px 30px;
			color: #00B26A;
		}
		button{
			margin-left:5%;
			width: 90%;
			height:40px;
			font-size: 16px;
			line-height: 40px;
			background-color: #52c693;
			color: #fff;
			border-radius: 20px;
		}
	}
		
}
</style>
