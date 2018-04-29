<template>
  <div class="hello">
  	
    <shopList></shopList>
    <Foot></Foot>
  </div>
</template>

<script>
import Foot from '../components/foot'
import shopList from '../components/shopList'
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    Foot,
    shopList
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #42b983;
}
</style>
