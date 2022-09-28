<template>
	<view class="charts-box">
		<qiun-data-charts type="column" :opts="opts" :chartData="chartData" />
	</view>
</template>

<script setup>
import { onReady } from '@dcloudio/uni-app'
import { ref, reactive, toRefs } from 'vue'

let chartData = ref({})
onReady(() => {
	getServerData()
})
// 自定义样式
const opts = {
	color: [
		'#1890FF',
		'#91CB74',
		'#FAC858',
		'#EE6666',
		'#73C0DE',
		'#3CA272',
		'#FC8452',
		'#9A60B4',
		'#ea7ccc',
	],
	padding: [15, 15, 0, 5],
	legend: {},
	xAxis: {
		disableGrid: true,
	},
	yAxis: {
		data: [
			{
				min: 0,
			},
		],
	},
	extra: {
		column: {
			type: 'meter',
			width: 30,
			activeBgColor: '#fff',
			activeBgOpacity: 1,
			meterBorder: 3,
			meterFillColor: '#21f',
		},
	},
}
const getServerData = () => {
	//模拟从服务器获取数据时的延时
	setTimeout(() => {
		let res = {
			categories: ['2016', '2017', '2018', '2019', '2020', '2021'],
			series: [
				{
					name: '目标值',
					data: [35, 36, 31, 33, 13, 34],
				},
				{
					name: '完成量',
					data: [18, 27, 21, 24, 6, 28],
				},
			],
		}
		chartData.value = res
		console.log(chartData)
	}, 500)
}
</script>

<style lang="scss">
.charts-box {
	width: 100%;
	height: 500rpx;
}
</style>
