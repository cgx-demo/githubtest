<template>
	<div class="foot">
		<ul class="list">
			<li style="border-left: none;"><router-link to="/">职位</router-link></li>
			<li><router-link to="/find">日程</router-link></li>
			<li><router-link to="/order">消息</router-link></li>
			<li><router-link to="/user">我的</router-link></li>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'foot',
		data () {
			return {
				
			}
		}
	}
</script>

<style scoped>
ul li{
	list-style: none;
}
a{
	text-decoration: none;
	color: #333;
	font-size: 28px;
}
.list{
	display: flex;
	position:fixed;
	bottom:0px;
	left: 0px;
	width: 100%;
	margin:0px;
	padding:0px;
	background: #F4F6F8;
}
.list>li{
	width: 25%;
	text-align: center;
	height: 0.88rem;
	line-height: 0.66rem;
	border: 1px solid #CCC;
	border-right: none;
	border-bottom: none;
}
.list>li>a{
	font-size: 0.32rem;
}
</style>