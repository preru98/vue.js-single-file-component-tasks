<template>
 <div>
  <!-- {{this.products}} -->
  <button v-for="(product,index) in products" v-on:click="showProduct(index)" :key="product.id">{{product.title}}</button>
  <toy-pi v-if="products.length" v-bind:img="products[selectedProduct].src" :name="products[selectedProduct].title"></toy-pi>
 </div>
</template>

<script>
import * as axios from 'axios'
import pi from './components/toy.vue'
export default {
    data:function(){
    return{
      products:[],
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
  },
  mounted: function () {
    const scope=this
    // this.$nextTick(function () {
        axios.get('http://localhost:3000/data')
          .then(function(response){    //anonymous  : resolving [this] conflict
            console.log(response.data);
            scope.products=response.data
            console.log(scope.products) //this.products
          })
          .catch(function (error) {
            console.log(error);
          })
    // })
  }
}
</script >

<style scoped>

</style>


