/**
* 话题分类
* Created by yxt
* 2017/1/21
**/

<template>
	<div class="userinfomation">
		<div class="user-top">
			<span>{{res.title1}}</span>
			<span>{{res.title2}}</span>
		</div>
		<div class="user-btm">
			<ul>
				<li v-for="item in res.content">
					<router-link tag="span" to="{path: 'username', query: {item.user_id}}" class="user-btm-title">{{item.username}}</router-link>
					<span>{{item.time}}</span>
					<p>{{item.article}}</p>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
import getCGI from '../../getCGI/Information'
import '../../static/lib/reset.css'

  let data = {
    list: []
  }
  getCGI(data)
	
	export default {
		name: 'userinfomation',
		data() {
			return {
				data: data,
				res: data.list[0]
			}
		},
		props: ['msg'],
		watch: {
			msg: 'judge'
		},
		methods: {
			judge: function (val) {
				this.res = this.data.list[val];
				//console.log(this.res.title1);
			}
		}
	}
</script>

<style lang="less">
	.userinfomation {
		margin: 70px auto 0;
		width: 85%;
		font-weight: 400;
		font-family: '微软雅黑';


		.user-top {
			width: 100%;
			height: 50px;
			border-bottom: 1px solid #ccc;
			background-color: white;
			span {
				display: inline-block;
				padding: 10px 30px;
				font-size: 1.3em;
			}
		}

		.user-btm {

			ul {
				width: 80%;
				margin: 0 auto;
			}
			
			li {
				margin: 10px 0;
				width: 100%;
				border-bottom: 1px solid #ccc;
				display: -webkit-box;
				-webkit-box-orient: vertical;
				-webkit-line-clamp: 3;
				overflow: hidden;
			}

			li:hover {
				background-color: #f2f2f5;
			}

			span {
				margin: 10px;
				font-size: 1.2em;
				color: #000;
			} 
			p {
				margin: 10px;
				font-size: 1.1em;
				color: #999;
				line-height: 28px;
			}
			.user-btm-title:hover {
				cursor: pointer;
				color: #eb7350;
			}
		}
	}
</style>