<template>
  <div id="login">
    <form @submit.prevent="onSubmitLogin">
        <fieldset>
            <legend>Login</legend>

            <label for="email">Email</label><br>
            <input v-model="email" type="email" id="email" name="email" required><br>

            <label for="password">Password</label><br>
            <input v-model="password" type="password" id="password" name="password" required><br>
            <input type="submit" value="LOG IN">
            <button v-on:click="notify">Sign up</button>
        </fieldset> 
    </form>  
  </div>

</template>

<script>
    export default {
        data:function(){
            return{
                email:null,
                password:null   
            }
        },
        methods:{
            onSubmitLogin:function(){
                alert('login successful'+ this.email)
                this.email=null
                this.password=null
            },
            notify:function(){
                this.$emit('toggle');
            }
        }
    }
</script>

<style>

</style>
