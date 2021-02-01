<template>
	<view>
		<!-- 轮播图模块 -->
		<swiper style="width:750rpx; height:250rpx;" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="200">
			<swiper-item>
				<image src="../../static/demo/banner/1.jpg" style="width: 100%; height: 250rpx;"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/demo/banner/2.jpg" style="width: 100%; height: 250rpx;"></image>
			</swiper-item>
		</swiper>
		
		<!-- 列表模块 -->
		<view class="flex flex-wrap">
			<view @click="openLive" v-for="(item,index) in 10" :key="index" style="width: 375rpx; height: 375rpx; padding: 5rpx; box-sizing: border-box; position: relative;">
				<!-- 直播间图片 -->
				<image src="../../static/demo/1.jpg" style="width: 365rpx; height: 365rpx;" class="rounded" mode="aspectFill"></image>
				<!-- 直播间金币 -->
				<view class="rounded-circle px-2 flex align-center justify-center" style="position: absolute; left: 15rpx; top: 15rpx; background-color: rgba(0,0,0,0.4);">
					<text class="iconfont iconbizhongguanli text-warning mr-1"></text>
					<text class="text-white font">0</text>
				</view>
				<!-- 直播间人气 -->
				<view class="rounded-circle px-2 flex align-center justify-center" style="position: absolute; right: 15rpx; top: 15rpx; background-color: rgba(0,0,0,0.4);">
					<text class="text-white font mr-1">人气:</text>
					<text class="text-white font">0</text>
				</view>
				<!-- 直播间名称 -->
				<view class="rounded-circle flex align-center justify-center" style="position: absolute; left: 15rpx; bottom: 15rpx; ">
					<text class="text-white font">标题</text>
				</view>
				<!-- 直播间状态 -->
				<view class="rounded-circle px-2 flex align-center justify-center" style="position: absolute; right: 15rpx; bottom: 15rpx; background-color: rgba(0,0,0,0.4);">
					<text style="width: 20rpx; height: 20rpx; display: block; " class="rounded-circle bg-danger mr-1"></text>
					<text class="text-white font">已结束</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			openLive(){
				uni.navigateTo({
					url : "../live/live"
				})
			}
		}
	}
</script>

<style>
	
</style>
