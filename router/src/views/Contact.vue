<template>
  <div class="contact">
    <p>Contact : prerna1998.ps@gmail.com</p>
    <button v-on:click="back">Back To Home</button>
  </div>
</template>

<script>
export default {
    methods:{
        back:function(){
            this.$router.push('/')
        }
    }
}
</script>
