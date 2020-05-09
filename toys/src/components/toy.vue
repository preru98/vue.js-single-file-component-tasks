<template>
    <div>
        <h3>{{this.name}}</h3>
        <img v-bind:src="this.img"/>
    </div>
</template>

<script>

export default {
    props:['img','name'],
    data:function(){
        return {
            // image:this.img,
            // title:this.name
        }
    },
    // methods:{
    //     image:function(){
    //         return this.img
    //     },
    //     title:function(){
    //         return this.name
    //     }
    // }
}
</script>

<style>
div{
    border:solid 1px grey;
}
img{
    width:75px;
    padding:12px;
    height:75px;
}
</style>
