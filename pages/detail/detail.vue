<template>
	<view>商品id:{{ data.detailVal.idx }}</view>
	<view class="a">商品名:{{ data.detailVal.name }}</view>
</template>

<script setup>
import { onLoad } from '@dcloudio/uni-app'
import { reactive } from 'vue'
const data = reactive({
	detailVal: {},
})
onLoad(optipn => {
	setTimeout(() => {
		console.log('🚀 ~ file: detail.vue ~ line 7 ~ optipn', optipn)
		data.detailVal = {
			idx: optipn.idx,
			name: '商品' + optipn.idx,
		}
	}, 1000)
})
</script>

<style lang="scss"></style>
