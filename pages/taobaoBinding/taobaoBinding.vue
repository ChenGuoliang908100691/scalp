<template>
	<view class="taobaoBinding">
		<view class="BH"></view>
		
		<view class="attention">
			<view class="content">
				<text class="cuIcon-warn text-green"></text>
				<text class="text-gray">注意事项</text>
			</view>
			<view class="text">
				账号审核时间周一至周五
				<text style="color: #00B26A;">9:00 - 18:00</text>
				账号提交后5个工作日内完成审核，如遇周末或节假日顺延，审核工作人工进行，用户请耐心等待！
			</view>
			<view class="warning">
				<view class="text">
					请正确填写信息，收货信息必须和京东收货地址一致，恶意乱填写，导致举报申诉的，一律永久冻结账户处理。
				</view>
				<view class="text">
					警告：收货人姓名手机收货地址都不能有重复，绑定两个账号的，收货信息必须填写不一样！
				</view>
			</view>
		</view>
		<view class="taobaoMessage">
			<view class="head">
				账户信息
			</view>
			<view class="content">
				<view class="cu-form-group">
					<view class="title">淘宝账号</view>
					<input placeholder="输入淘宝账号" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">个人姓名</view>
					<input placeholder="输入姓名" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">手机号码</view>
					<input placeholder="输入手机号码" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">验证号码</view>
					<input placeholder="输入验证码" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">所在市区</view>
					<input placeholder="输入所在省市/区" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">详细地址</view>
					<input placeholder="输入详细地址" name="input"></input>
				</view>
			</view>
		</view>
		<view class="authentication">
			<view class="head">
				淘宝账号信息认证
			</view>
			<view class="QRcode">
				<img src="@/imgs/8.jpg"></img>
			</view>
			<view class="text">
				保存二维码,用需要绑定的淘宝账号扫码'确认登陆'后即可点击下方提交按钮.
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
	.taobaoBinding{
		.BH {
			background-color: #F1F1F1;
			height: 5px;
		}
		.attention{
			.content{
				height:30px;
				line-height: 30px;
				padding: 0 15px;
			}
			.text{
				padding: 0 15px;
				color: gray;
			}
			.warning{
				padding: 10px 0;
				.text{
					padding-top: 10px;
					color: red;
				}
			}
		}
		.taobaoMessage{
			.head{
				font-size: 14px;
				font-weight: 600;
				height:30px;
				line-height: 30px;
				text-align: center;
			}
		}
		.authentication{
			padding-bottom: 20px;
			.head{
				font-size: 14px;
				font-weight: 600;
				height:30px;
				line-height: 30px;
				text-align: center;
			}
			.QRcode{
				text-align: center;
				img{
					width: 180px;
					height: 180px;
					border: 2px solid #52c693;
					padding: 2px;
					margin: 0px 0 25px;
					}
			}
			.text{
				font-weight: 600;
				padding: 0 15px;
				font-size: 16px;
			}
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
