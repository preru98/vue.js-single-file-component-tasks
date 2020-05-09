<template>
  <div id="sign">
    <form v-on:submit.prevent="onSubmitLogin">
        <fieldset>
            <legend>Sign Up</legend>

            <label for="email">Email</label><br>
            <input v-model="email" type="email" id="email" name="email" required><br>

            <label for="password">Password</label><br>
            <input v-model="password" type="password" id="password" name="password" required><br>

            <label for="c-password">Confirm Password</label><br>
            <input v-model="confirmPassword" type="password" id="c-password" name="c-password" required><br>
            <input type="submit" value="SIGN UP">
            <button v-on:click="notify">Login</button>
            
        </fieldset> 
    </form>  
  </div>

</template>

<script>
    export default {
        data:function(){
            return{
                email:null,
                password:null,   
                confirmPassword:null
            }
        },
        methods:{
            onSubmitLogin:function(){
                alert('sign up successful'+ this.email)
                this.email=null
                this.password=null
                this.confirmPassword=null
            },
            notify:function(){
                this.$emit('toggle');
            }
        }
    }
</script>

<style>

</style>
