<template>
  <div class="hello">
    <mu-rotation></mu-rotation>
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <button></button>
  </div>
</template>

<script>
import Rotation from '@/components/Rotation'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'test music website'
    }
  },
  components:{
    'mu-rotation':Rotation
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import '../css/set';
button{
  width: 200px;
  height: 30px;
}
h1, h2 {
  font-weight: normal;
}
h1{
  color: $redColor;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
