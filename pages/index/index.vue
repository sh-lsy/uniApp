<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{ title }}</text>
		</view>
		<view class="test">
			<button type="primary" @tap="change">tap操作</button>
			<button type="primary" @click="change">tap操作</button>
			<view class="box" :class="{active: isActive}"></view>
		</view>
	</view>
</template>

<script setup>
import {ref} from 'vue'
	const title = ref('hello vue3-uniApp')
	const isActive = ref(false)
	const change = () =>{
		isActive.value = !isActive.value
	}
</script>

<style>
.content {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}

.logo {
	height: 200rpx;
	width: 200rpx;
	margin-top: 200rpx;
	margin-left: auto;
	margin-right: auto;
	margin-bottom: 50rpx;
}

.text-area {
	display: flex;
	justify-content: center;
}

.title {
	font-size: 36rpx;
	color: #8f8f94;
}
.test {
	width: 100%;
	
}
button {
	margin-bottom: 10px;
}
.box {
	height: 100rpx;
	background-color: darkkhaki;
}
.active{
	background-color: aqua;
}
</style>
