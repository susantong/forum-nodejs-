/**
* 话题分类
* Created by yxt
* 2017/1/21
**/

<template>
	<div class="mynews">
		<h2>我的消息箱</h2>
		<ul class="mynews-top">
			<li @click="up(0)" class="active"><p>@我的</p></li>
			<li @click="up(1)"><p>评论</p></li>
			<li @click="up(2)"><p>赞</p></li>
			<span></span>
			<li @click="up(3)"><p>私信</p></li>
			<li @click="up(4)"><p>群通知</p></li>
			<li @click="up(5)"><p>系统消息</p></li>
		</ul>
	</div>
</template>

<script>
import '../../static/lib/reset.css'

	export default {
		name: 'mynews',
		data() {
			return {
				data: [0, 1, 2, 3, 4, 5]
			}
		},
		props: ['msg'],
		methods: {
			up(index) {
				$('li').eq(index).addClass('active').siblings().removeClass('active');
				this.$emit('upup', this.data[index]);
			}
		}
	}
</script>

<style lang="less">
	.mynews {
		width: 15%;
		background-color: #93c5e3;
		color: #fff;
		font-size: 1.2em;
		margin-top: 70px;
		padding-bottom: 10px;

		li {
			height: 34px;
			overflow: hidden;
			line-height: 34px;
		}

		h2 {
			font-size: 1.3em;
			text-align: center;
			padding-top: 10px;
		}

		p {
			margin-left: 35%;
		}
		
		.active, li:hover {
			background-color: rgba(255,255,255,0.2);
			cursor: pointer;
			width: 100%;
		}

		span {
			display: inline-block;
			height: 1px;
			background-color: rgba(255,255,255,0.2);
			width: 100%;
		}
	}
</style>