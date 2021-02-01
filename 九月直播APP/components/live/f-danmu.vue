<template>
	<view  style="position: fixed; bottom:120rpx; left: 0; right:0; ">
		<scroll-view :scroll-into-view="scrollIntoView" scroll-y="true" style="width: 520rpx; height: 300rpx;" scroll-with-animation class="pl-3">
			<view :id="'danmu' + item.id" v-for="(item,index) in list" :key="index" class="flex justify-start align-center rounded p-2 mb-2" style="background-color: rgba(255,255,255,0.125);">
				<text class="font-md text-danger">{{item.name}}:</text>
				<text class="font-md text-white">{{item.content}}</text>
			</view>
		</scroll-view>
	</view>
</template>

<script>
export default {
	data(){
		return {
			scrollIntoView : "",
			list : [
				
			]
		}
	},
	mounted(){
		// let id = 1;
		// //由于弹幕的数据都是从后端传递过来了,所以我们在这只是先进行模拟一下
		// setInterval(()=>{
			// this.list.push({
			// 		id : id,
			// 		name : "昵称" + id,
			// 		content : "九月直播666"
			// 	})
		// 	//调用置于底部方法	
		// 	this.toBottom();	
		// 	id++
		// },1000)
	},
	methods:{
		//发送弹幕方法
		send(data){
			this.list.push(data)
			this.toBottom()
		},
		//置于底部风发
		toBottom(){
			setTimeout(()=>{
				let len = this.list.length;
				if(len > 0 && this.list[len - 1]){
					this.scrollIntoView = 'danmu' + this.list[len - 1].id;
				}
			},200)
			
		}
	}
}
</script>

<style>
</style>
