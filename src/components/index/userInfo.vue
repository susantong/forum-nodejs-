/**
* 登录
* Created by yxt
* 2016/12/12
**/

<template>
	<div class="wrap">
		<router-link to="user" tag="div" class="title"><img src="../../static/images/title.gif" width="60" height="60"></router-link>
		<router-link to="{path: 'user', query: {user_id: data.list.username_id}}" tag="h2" class="user">{{data.list.username}}</router-link>
		<ul>
			<router-link to="user" tag="li">
				<p class="count">{{data.list.focus_count}}</p>
				<p>关注</p>
			</router-link>
			<router-link to="user" tag="li">
				<p class="count">{{data.list.fans}}</p>
				<p>粉丝</p>
			</router-link>
			<router-link to="user" tag="li">
				<p class="count">{{data.list.weibo}}</p>
				<p>微博</p>
			</router-link>
		</ul>
	</div>
</template>

<script>
	import getCGI from '../../getCGI/userInfo'
	let data = {
		list: {}
	};
	getCGI(data);
	export default {
		name: 'userinfo',
		data() {
			return {
				data: data
			}
		}
	}
</script>

<style lang="less">
	.wrap {
		li {
			list-style: none;
		}
		.clearfix {
      *zoom: 1;

      &:before, &:after { 
        content: "";
        display: table;
      }

      &:after {
        clear: both;
        overflow: hidden;
      }
    }
		width: 30%;
		.title {
			width: 60px;
			height: 60px;
			margin: 0 auto;
			border-radius: 50%;
			overflow: hidden;
			cursor: pointer;
		}
		.user {
			text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
      text-align: center;
      cursor: pointer;
      margin: 10px auto;
      font-size: 1.4em;
      &:hover {
      	color: #eb7350;
      }
		}

		ul {
			.clearfix;
			width: 90%;
			margin: 10px auto;
			li {
				float: left;
				width: 30%;
				text-align: center;
				cursor: pointer;
				&:hover .count{
					color: #eb7350;
				}
				.count {
					font-weight: bold;
					font-size: 1.4em;
				}
			}
		}
	}
</style>