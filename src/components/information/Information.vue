/**
* 话题分类
* Created by yxt
* 2017/1/21
**/

<template>
	<div class="information">
		<mynews @upup="change" class="left"></mynews>
		<userinfomation :msg="msg" class="right"></userinfomation>
	</div>
</template>

<script>
	import Userinfomation from './Userinfomation.vue'
	import myNews from './myNews.vue'
	import '../../static/lib/reset.css'

	export default {
		name: 'information',
		components: {
			userinfomation: Userinfomation,
			mynews: myNews
		},
		data() {
			return {
				msg: ''
			}
		},
		methods: {
			change(msg) {
				this.msg = msg;
				//console.log(this.msg);
			}
		}
		// watch: {
		// 	msg: function (val) {
		// 		console.log(val);
		// 	}
		// }
		
	}
</script>

<style lang="less">
	.information {
		overflow: hidden;
		width: 80%;
		margin: 0 auto;
		.left {
			float: left;
		}
		.right {
			float: left;
		}
	}
</style>