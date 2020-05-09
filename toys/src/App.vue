<template>
 <div>
  <button v-for="(product,index) in products" v-on:click="showProduct(index)" :key="product.id">{{product.title}}</button>
  <toy-pi v-bind:img="products[selectedProduct].src" :name="products[selectedProduct].title"></toy-pi>
 </div>
</template>

<script>
import pi from './components/toy.vue'
export default {
  
  data:function(){
    return{
      products:[
        { 
          src:'https://image.made-in-china.com/202f0j00KuiUItdAEcbk/Custom-Stuffed-Animal-Toys-Gift-Plush-Animal-Baby-Doll-Fat-White-Plush-Sheep-Set-Cute-Plush-Lamb-in-Different-Size.jpg',
          title:'sheep',
          id:67
        },
         {
          src:'https://www.cyrenanime.com/storage/photos/58/1-3258.jpg',
          title:'Bunny',
          id:89
        },
         {
          src:'https://images-na.ssl-images-amazon.com/images/I/41qLw8JNNKL.jpg',
          title:'Pingu',
          id:90
        }
      ],
      selectedProduct:0
    }
  }, 
  components:{
    'toy-pi':pi
  },
  methods:{
    showProduct:function(index){
      this.selectedProduct=index
    }
  }
}
</script>

<style>
</style>
