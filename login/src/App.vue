<template>
  <div>
    <login-user v-if="!currentForm" v-on:toggle="shuffle" ></login-user>
    <sign-up v-else v-on:toggle="shuffle"></sign-up>
  </div>
</template>

<script>
import login from './components/login.vue'
import sign from './components/sign.vue'

  export default {
    components:{
      'login-user':login,
      'sign-up':sign
    },
    data:function(){
      return{
        currentForm:0
      }
    },
    methods:{
      shuffle:function(){
        this.currentForm=!this.currentForm
      }
    }
  }
</script>

<style>
</style>
