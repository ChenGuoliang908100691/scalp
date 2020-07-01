<template>
	<view class="accountMessage">
		<view class="title">
			<view class="title1">
				根据国家网信办新规，平台进行实名安全工作，当您的账户出现风险时，在必要时系统会要求您进行更高级别的认证。
			</view>
			<view class="title2">
				我们承诺保障您账户的资金安全，且不会泄漏您的个人隐私，请您积极配合。
			</view>
			<view class="title3">
				如果前置摄像无法上传请使用后置拍摄
			</view>
		</view>
		
		<view class="identityCard">
			<view class="cu-bar bg-white margin-top">
				<view class="action">
					上传身份张照片（正面和反面）
				</view>
				<view class="action">
					{{identityCardimgList.length}}/2
				</view>
			</view>
			<view class="cu-form-group">
				<view class="grid col-4 grid-square flex-sub">
					<view class="bg-img" v-for="(item,index) in identityCardimgList" :key="index" @tap="ViewImage" :data-url="identityCardimgList[index]">
					 <image :src="identityCardimgList[index]" mode="aspectFill"></image>
						<view class="cu-tag bg-red" @tap.stop="DelImg" :data-index="index">
							<text class='cuIcon-close'></text>
						</view>
					</view>
					<view class="solids" @tap="ChooseImage" v-if="identityCardimgList.length<2">
						<text class='cuIcon-cameraadd'></text>
					</view>
				</view>
			</view>
		</view>
		
		<view class="BH"></view>
		
		<view class="personalInformation">
			<view class="cu-form-group">
				<view class="title">真实姓名</view>
				<input placeholder="输入真实姓名" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">身份证号</view>
				<input placeholder="输入身份证号" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">家庭住址</view>
				<input placeholder="输入家庭住址" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">出生日期</view>
				<input placeholder="输入出生日期" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">个人性别</view>
				<input placeholder="输入性别" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">个人民族</view>
				<input placeholder="输入民族" name="input"></input>
			</view>
			
		</view>
		
		<view class="BH"></view>
		
		<view class="content">
			<text class="cuIcon-warn text-green"></text>
			<text class="text-red">姓名和身份证一样，银行卡务必准确。</text>
		</view>
		
		<view class="BH"></view>
		
		<view class="bankCard ">
			<view class="cu-bar bg-white margin-top">
				<view class="action">
					上传银行卡照片
				</view>
				<view class="action">
					{{bankCardimgList.length}}/1
				</view>
			</view>
			<view class="cu-form-group">
				<view class="grid col-4 grid-square flex-sub">
					<view class="bg-img" v-for="(item,index) in bankCardimgList" :key="index" @tap="ViewImage1" :data-url="bankCardimgList[index]">
					 <image :src="bankCardimgList[index]" mode="aspectFill"></image>
						<view class="cu-tag bg-red" @tap.stop="DelImg1" :data-index="index">
							<text class='cuIcon-close'></text>
						</view>
					</view>
					<view class="solids" @tap="ChooseImage1" v-if="bankCardimgList.length<1">
						<text class='cuIcon-cameraadd'></text>
					</view>
				</view>
			</view>
		</view>
		
		<view class="bankCardInformation">
			<view class="cu-form-group">
				<view class="title">银行卡号</view>
				<input placeholder="输入银行卡号" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">确认卡号</view>
				<input placeholder="输入银行卡号" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">所属银行</view>
				<input placeholder="输入所属银行" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">所在城市</view>
				<input placeholder="输入所在城市" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">支行名称</view>
				<input placeholder="输入支行名称" name="input"></input>
			</view>
		</view>
		<view class="base">
			<view class="title">平台支持四大银行绑定</view>
			<view class="text">1.中国银行</view>
			<view class="text">2.中国农业银行</view>
			<view class="text">3.中国工商银行</view>
			<view class="text">4.中国建设银行</view>
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
				menuArrow: false,
				identityCardimgList: [],
				bankCardimgList:[]
			}
		},
		onLoad() {
			
		},
		onShow() {
			
		},
		methods:{
			ChooseImage() {
				uni.chooseImage({
					count: 4, //默认9
					sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
					sourceType: ['album'], //从相册选择
					success: (res) => {
						if (this.identityCardimgList.length != 0) {
							this.identityCardimgList = this.identityCardimgList.concat(res.tempFilePaths)
						} else {
							this.identityCardimgList = res.tempFilePaths
						}
					}
				});
			},
			ViewImage(e) {
				uni.previewImage({
					urls: this.identityCardimgList,
					current: e.currentTarget.dataset.url
				});
			},
			DelImg(e) {
				uni.showModal({
					title: '提示',
					content: '确定要删除这张图片吗？',
					cancelText: '取消',
					confirmText: '确定',
					success: res => {
						if (res.confirm) {
							this.identityCardimgList.splice(e.currentTarget.dataset.index, 1)
						}
					}
				})
			},
			
			ChooseImage1() {
				uni.chooseImage({
					count: 4, //默认9
					sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
					sourceType: ['album'], //从相册选择
					success: (res) => {
						if (this.bankCardimgList.length != 0) {
							this.bankCardimgList = this.bankCardimgList.concat(res.tempFilePaths)
						} else {
							this.bankCardimgList = res.tempFilePaths
						}
					}
				});
			},
			ViewImage1(e) {
				uni.previewImage({
					urls: this.bankCardimgList,
					current: e.currentTarget.dataset.url
				});
			},
			DelImg1(e) {
				uni.showModal({
					title: '提示',
					content: '确定要删除这张图片吗？',
					cancelText: '取消',
					confirmText: '确定',
					success: res => {
						if (res.confirm) {
							this.bankCardimgList.splice(e.currentTarget.dataset.index, 1)
						}
					}
				})
			},
			
		}
	}
</script>

<style lang="less">
	.accountMessage{
		width: 100%;
		height:100%;
		.BH {
			background-color: #F1F1F1;
			height: 5px;
		}
		.title{
			.title1{
				margin-top: 10px;
				padding:0 10px;
				color: gray;
			}
			.title2{
				padding:5px 10px;
				color: gray;
			}
			.title3{
				padding:5px 10px;
				color: red;
			}
		}
		.identityCard{
			
		}
		.personalInformation{
			
		}
		.content{
			height:30px;
			line-height: 30px;
			padding: 0 15px;
		}
		.base{
			padding:0 10px;
			padding-bottom: 20px;
			.title{
				font-weight: 600;
				height:30px;
				line-height: 30px;;
				font-size: 16px;
				text-align: center;
			}
			.text{
				margin-left: 35%;
				color: red;
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
