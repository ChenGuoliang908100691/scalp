<template>
	<view class="cu-bar tabbar bg-white">
		<view class="action" :class="{'text-gray':index==now_page_index}" v-for="(item,index) in list" @tap="toNav(item)">
			<view class="cu-btn">{{item.title}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				now_page_index:0,
				list:[
					{
						title:'首页',
						num:0,
						path:'../../index/index'
					},
					{
						title:'接单',
						num:1,
						path:'../pages/index/index'
					},
					{
						title:'我的',
						num:2,
						path:'../user/reseller/reseller'
					}
				]
			}
		},
		onShow() {
			
		},
		mounted() {
			
		},
		methods: {
			toNav(item){
				console.log(item)
					this.now_page_index = item.num
					uni.redirectTo({
						url:item.path
					})
					
			}
		}
	}
</script>

<style lang="scss" scoped>
	.cu-bar{
		border-top: 1px solid #f1f1f1;
		position: fixed;
		width: 100%;
		left:0;
		bottom: 0;
		color: #2E8B57;
		font-weight: 600;
		view:nth-child(2){
			view{
				width:50px;
				height:50px;
				border: 1px solid green;
				border-radius: 50%;
				background-color: #2E8B57;
				color: #fff;
			}
		}
		view:nth-child(1){
			
			view{
				background-color: #fff;
				
			}
		}
		view:nth-child(3){
			view{
				background-color: #fff;
			}
		}
	}
		
	
</style>
