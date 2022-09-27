<template>
	<view>
		<view class="cake-wra">
			<view class="cake-item" v-for="i in 8" :key="i">
        <view class="poster">
          
        </view>
        <view class="info-cont">
          <view class="info">
            <view class="fs-28">
              草莓蛋糕
            </view>
            <view class="fs-16">
              CaoMei DanGao
            </view>
            <view class="fs-18">
              <text class="fs-14">￥</text>
              218.00
            </view>
          </view>
          <view class="cart-btn">
            
          </view>
        </view>
			</view>
		</view>
	</view>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.cake-wra {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 15rpx;
  .cake-item {
    .poster {
      width: 350rpx;
      height: 350rpx;
      background-color: #f5f5f5;
    }
    .fs-28 {
      margin-top: 20rpx;
    }
    .fs-16 {
      margin: 10rpx 0;
    }
    .fs-18 {
      margin-bottom: 20rpx;
    }
  }
}
</style>
