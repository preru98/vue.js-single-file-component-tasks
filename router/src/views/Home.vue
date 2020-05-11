<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h3>Hi, {{username}} Welcome!</h3>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data:function(){
    return{
      username:"user"
    }
  },
  mounted:function(){
    this.username=localStorage.getItem('username');
    alert(this.username)
  }
}
</script>
