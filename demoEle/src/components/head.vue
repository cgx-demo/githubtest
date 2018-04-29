<template>
	<div class="head">
		<header class="head_top">
			 <section class="head_goback" v-if="goBack" @click="$router.go(-1)">
	            <svg width="100%" height="100%" xmlns="http://www.w3.org/2000/svg" version="1.1">
	                <polyline points="12,18 4,9 12,0" style="fill:none;stroke:rgb(255,255,255);stroke-width:2"/>
	            </svg>
	       </section>
	        <section class="title_head ellipsis" v-if="headTitle">
            	<span class="title_text">{{headTitle}}</span>
        	</section>
		</header>
	</div>
</template>

<script>
	export default{
		name:"head",
		data () {
			return {
				msg:'header'
			}
		},
		props:["goBack","headTitle"]
	}
</script>

<style scoped>

.head_top{
	position: fixed;
	top: 0;
	left: 0;
	margin: 0;
	padding: 0;
	width: 100%;
	height: 0.44rem;
	line-height: 0.44rem;
	display: flex;
	background: #C1C1C1;
}
.head_goback{
	width: 0.24rem;
	height: 0.24rem;
	margin: 0.1rem;
}
.title_head{
	width: 100%;
	text-align: center;
	font-size: 0.16rem;
}
</style>
