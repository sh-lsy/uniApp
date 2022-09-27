<template>
	<view class="person-wra">
		<view class="bg"></view>
		<view class="logo">
			<image :src="logoUrl"></image>
			<view class="name">skye</view>
			<view class="content">
				<view v-for="(item, index) in funList" :key="index" class="item">
					<span class="iconfont" :class="item.font"></span>
					<span>{{ item.title }}</span>
				</view>
			</view>
		</view>
	</view>
</template>

<script setup>
import { ref, onMounted, reactive } from 'vue'
const logoUrl = ref('')
// 获取本地图片url
const getUrl = async () => {
	const img = await import('../../static/logo.jpg')
	logoUrl.value = img.default
}
// 功能菜单
const funList = reactive([
	{
		font: 'icon-wodedingdan0101',
		title: '我的订单',
	},
	{
		font: 'icon-daifukuan',
		title: '待付款',
	},
	{
		font: 'icon-daishouhuo',
		title: '待收货',
	},
	{
		font: 'icon-01_huiyuandengjiguanli',
		title: '会员等级',
	},
	{
		font: 'icon-jifen',
		title: '积分',
	},
	{
		font: 'icon-yue',
		title: '余额',
	},
	{
		font: 'icon-hongbao',
		title: '红包/优惠券',
	},
	{
		font: 'icon-yinhangqia',
		title: '现金卡',
	},
])

onMounted(() => {
	getUrl()
})
</script>

<style lang="scss" scoped>
page {
	background-color: #fff;
}

.person-wra {
	display: flex;
	flex-direction: column;
	align-items: center;
	.bg {
		height: 400rpx;
		width: 100%;
		background-color: rgb(0, 0, 0, 0.05);
		position: absolute;
		z-index: 0;
	}
	.logo {
		margin-top: 200rpx;
		background-color: #fff;
		// height: 200rpx;
		width: 96%;
		text-align: center;
		position: relative;
		z-index: 1;
		box-shadow: 0 1px 6px rgb(0, 0, 0, 0.2);
		image {
			width: 200rpx;
			height: 200rpx;
			border-radius: 50%;
			margin-top: -100rpx;
		}
		.name {
			font-size: 40rpx;
		}
		.content {
			display: flex;
			flex-wrap: wrap;
			padding: 30rpx;
			margin-top: 40rpx;
			.item {
				width: 25%;
				display: flex;
				flex-direction: column;
				align-items: center;
				color: gray;
				padding: 12rpx 0;
				font-size: 28rpx;
				cursor: pointer;
				.iconfont {
					font-size: 80rpx;
					margin-bottom: 12rpx;
				}
				&:not(:nth-child(4n)) {
					border-right: 1rpx solid #d9d9d9;
				}
				&:nth-child(-n + 4) {
					border-bottom: 1rpx solid #d9d9d9;
				}
			}
		}
	}
}
</style>
