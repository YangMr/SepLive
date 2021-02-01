<script>
	export default {
		onLaunch: function() {
			//处理nvue加载自定义图标
			const domModule = weex.requireModule('dom')
			domModule.addRule('fontFace', {
			    'fontFamily': "iconfont",
			    'src': "url('http://at.alicdn.com/t/font_1859985_7mxozsfdvib.ttf')"
			});
			
			//监听中间按钮的点击事件
			uni.onTabBarMidButtonTap(function(){
				console.log("点击了中间按钮")
			})
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/* 公共样式 */
	@import url("./common/free.css");
	/* 主题样式 */
	@import url("./common/common.css");
	/* 字体图标 */
	/* #ifndef APP-PLUS-NVUE */
	@import url("/common/icon.css");
	/* #endif */
</style>
