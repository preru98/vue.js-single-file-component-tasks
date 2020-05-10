<template>
    <div>
        <h3>{{title}}</h3>
        <img v-bind:src="image"/>
    </div>
</template>

<script>

export default {
    props:['img','name'],
    data:function(){
        return {
            // image:this.img, //Won't work since data is constant
            // title:this.name
        }
    },
    // methods:{               //Definitely work : call the function in template : image() and title()
    //     image:function(){
    //         return this.img
    //     },
    //     title:function(){
    //         return this.name
    //     }
    // },
    computed:{                  //Definitely work : reference the property aas image and title
        image:function(){
            return this.img
        },
        title:function(){
            return this.name
        }
    }
}
</script>

<style scoped>
div{
    border:solid 1px grey;
}
img{
    width:75px;
    padding:12px;
    height:75px;
}
</style>
