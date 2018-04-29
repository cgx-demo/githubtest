<template>
	<div class="shop">
		<div class="headTitle">
			<input type="text" class="searchBox"/>
		</div>
		<positions></positions>
		
	</div>
</template>

<script>
import positions from '../components/position'
export default{
	name:"shop",
	data () {
		return {
			
		}
	},
	components:{
		positions
	}
}
</script>

<style scoped>
.headTitle{
	width: 100%;
	height: 0.88rem;
	display: flex;
	background: #FBB03B ;
	position: fixed;
	top: 0;
	
}
.searchBox{
	width: 80%;
	height:0.6rem;
	border: 1px solid #CCC;
	margin:0.14rem 10% 0;
	border-radius: 0.1rem;
	padding-left: 0.3rem;
}
.search{
	width: 0.3rem;
	height: 0.3rem;
	margin: 0.28rem 0.28rem 0 0;
	background: lightcyan;
}

</style>
