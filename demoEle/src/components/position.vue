<template>
	<div class="position">
		<ul class="shoplist">
			<li v-for="item of positionArr">
				<router-link to="/">					
					<div class="liCnt">						
						<div class="titleBox">
							<p class="title" v-html="item.name">web前端Vue.js开发工程事</p>
							<p class="icon"></p>
							<p class="money" v-html="item.salary_desc">20-50K</p>
						</div>
					</div>
					<img :src="'http://m.ccctuan.com/'+item.Logo" alt="" class="liImg" v-show="item.Logo"/>
				</router-link>
			</li>
			<p class="login"></p>
		</ul>
	</div>
</template>

<script>
import axios from 'axios'
export default {
	name: 'position',
	data () {
		return {
			positionArr:[],
			page:1,
			size:20,
			flag:true
		}
	},
	created (){
		this.getDate()
		this.winscroll()
	},
	methods:{
		getDate:function (){
			let that = this;
			let url="http://m.ccctuan.com/api/jobmen/search/noUserSearch/1";
			let param={"positionName":'',"expectSalary":'',"workPlace":'',"pageNum":this.page,"pageSize":this.size};
			this.flag=false;
			axios.post(url,param).then(function (res){
				console.log(res.data);
				that.positionArr=that.positionArr.concat(res.data.data);
				that.page++
				that.flag=true
			});
		},
		winscroll:function (){
			let that=this;
			document.onscroll=function (){
				var wScrollY = window.scrollY; // 当前滚动条位置    
			    var wInnerH = window.innerHeight; // 设备窗口的高度（不会变）    
			    var bScrollH = document.body.scrollHeight; // 滚动条总高度        
			    if (wScrollY + wInnerH >= bScrollH-80 && that.flag) {            
			        that.getDate()
			    }    
			}
		}
	}
}
</script>

<style scoped>
.position{
	background: #f3f5f7;
	width: 100%;
	height: 100%;
	padding-bottom: 0.5rem;
}
.titleBox{
	display: flex;
}
.icon{
	width: 0.3rem;
	height: 0.4rem;
	margin: 0 0.1rem;
	background: lightcyan;
}
.money{
	width: 1.4rem;
    margin-right: 0.1rem;
    font-size: 0.2rem;
    color: #FBB03B;
    text-align: center;
}
.liCnt{
	margin-top: 0.1rem;
}
.shoplist{
	width: 100%;
	margin:0.88rem 0;
	
}
.shoplist>li{
	height: 1.2rem;
	margin: 0.2rem;
	border-radius: 0.1rem;
	background: #fff;
}
.shoplist>li>a{
	display: flex;
	padding: 0 0.2rem;
}
.liImg{
	width: 0.8rem;
	height: 0.8rem;
	margin: 0.1rem;
}
.liCnt{
	width: 100%;
}
.title{
	font-size: 0.28rem;
    color: #666;
}
.login{
	width: 0.8rem;
	height: 0.8rem;
	background: url(../img/load_more.png) no-repeat;
	background-size: 100%;
	animation: login 1s infinite linear;
	text-align: center;
	margin-left: 40%;
}
@keyframes login{
	0% {
		transform: rotate(0deg);
	}
	100%{
		transform: rotate(360deg);
	}
}
</style>