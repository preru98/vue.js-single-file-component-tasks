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
        </fieldset> 
    </form>  
  </div>

</template>

<script>
import * as axios from 'axios'
    export default {
        data:function(){
            return{
                email:null,
                password:null   
            }
        },
        methods:{
            onSubmitLogin:function(){
                const scope=this
                alert('login successful '+ this.email+' will send data now')

                axios.post('http://localhost:3000/data', {
                    // email: this.email,
                    // password: this.password
                        src: "https://images-na.ssl-images-amazon.com/images/I/41qLw8JNNKL.jpg",
                        title: "Pingu",
                        id: "9084"
                })
                .then(function (response) {
                    alert(response.status)
                })
                .catch(function (error) {
                    console.log(error)
                });
                this.email=null
                this.password=null
            }
        }
    }
</script>

<style>

</style>
