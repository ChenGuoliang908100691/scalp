<template>
	<view class="jingdongBinding">
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
		</view>
		<view class="example" @click="toJDexample">
			进入查看绑定要求
		</view>
		<view class="warning">
			<view class="text">
				请正确填写信息，收货信息必须和京东收货地址一致，恶意乱填写，导致举报申诉的，一律永久冻结账户处理。
			</view>
			<view class="text">
				警告：收货人姓名手机收货地址都不能有重复，绑定两个账号的，收货信息必须填写不一样！
			</view>
		</view>
		<view class="jingdongMessage">
			<view class="head">
				账户信息
			</view>
			<view class="content">
				<view class="cu-form-group">
					<view class="title">京东账号</view>
					<input placeholder="输入京东账号" name="input"></input>
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
					<input placeholder="输入省市/区" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">详细地址</view>
					<input placeholder="输入详细地址" name="input"></input>
				</view>
			</view>
		</view>
		<view class="property">
			<view class="head">
				账号属性（与实名认证的省份信息一致）
			</view>
			<view class="content">
				<view class="cu-form-group">
					<view class="title">性别</view>
					<input placeholder="输入性别" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">年龄</view>
					<input placeholder="输入年龄" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">等级</view>
					<input placeholder="输入等级" name="input"></input>
				</view>
			</view>
		</view>
		<view class="uploadPictures">
			<view class="cu-bar bg-white margin-top">
				<view class="action">
					分别上传：（京东账户）（京东等级）（实名认证）（京东白条）
				</view>
				<view class="action">
					{{imgList.length}}/4
				</view>
			</view>
			<view class="cu-form-group">
				<view class="grid col-4 grid-square flex-sub">
					<view class="bg-img" v-for="(item,index) in imgList" :key="index" @tap="ViewImage" :data-url="imgList[index]">
					 <image :src="imgList[index]" mode="aspectFill"></image>
						<view class="cu-tag bg-red" @tap.stop="DelImg" :data-index="index">
							<text class='cuIcon-close'></text>
						</view>
					</view>
					<view class="solids" @tap="ChooseImage" v-if="imgList.length<4">
						<text class='cuIcon-cameraadd'></text>
					</view>
				</view>
			</view>
			<view class="text">
				京东白条:选填,开通京东白条账户接单可获取更多佣金
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
				imgList: [],
			}
		},
		onLoad() {
			
		},
		onShow() {
			
		},
		methods:{
			toJDexample(){
				uni.navigateTo({
					url:'../example/JDexample'
				})
			},
			ChooseImage() {
				uni.chooseImage({
					count: 4, //默认9
					sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
					sourceType: ['album'], //从相册选择
					success: (res) => {
						if (this.imgList.length != 0) {
							this.imgList = this.imgList.concat(res.tempFilePaths)
						} else {
							this.imgList = res.tempFilePaths
						}
					}
				});
			},
			ViewImage(e) {
				uni.previewImage({
					urls: this.imgList,
					current: e.currentTarget.dataset.url
				});
			},
			DelImg(e) {
				uni.showModal({
					title: '召唤师',
					content: '确定要删除这段回忆吗？',
					cancelText: '再看看',
					confirmText: '再见',
					success: res => {
						if (res.confirm) {
							this.imgList.splice(e.currentTarget.dataset.index, 1)
						}
					}
				})
			},
		}
	}
</script>

<style lang="less">
	.jingdongBinding{
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
		}
		.example{
			font-size: 16px;
			font-weight: 600;
			margin-top: 20px;
			height:40px;
			line-height: 40px;
			text-align: center;
			background-color: #00B26A;
			color: #ffffff;
		}
		.warning{
			padding: 10px 10px;
			.text{
				padding-top: 10px;
				color: red;
			}
		}
		.jingdongMessage{
			.head{
				font-size: 14px;
				font-weight: 600;
				height:30px;
				line-height: 30px;
				text-align: center;
			}
		}
		.property{
			.head{
				font-size: 14px;
				font-weight: 600;
				height:30px;
				line-height: 30px;
				text-align: center;
			}
		}
		.uploadPictures{
			padding-bottom: 30px;
			.text{
				padding: 0 15px;
				color: #00B26A;
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
