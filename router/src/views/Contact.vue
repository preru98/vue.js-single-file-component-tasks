<template>
  <div class="contact">
    <p>Contact : prerna1998.ps@gmail.com</p>
    <button v-on:click="back">Back To Home</button>
    <br><br>
    <form v-on:submit.prevent="save">
      <label for="username">Username</label> : 
      <input type="text" id="username" name="username" v-model="username">
      <input type="submit" value="Submit">
    </form>
  </div>
</template>

<script>
export default {
    data:function(){
      return {
        username:null
      }
    },
    methods:{
        back:function(){
          this.$router.push('/')
        },
        save:function(){
          localStorage.setItem('username', this.username);
        }
    }
}
</script>
