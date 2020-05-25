<template>
  <div>
    <h2>FAKE Taobao</h2>
    <ul>
      <li v-for="(good,index) in goods" :key="index">
        {{good.text}}
         | 
         {{good.price}}
         <button @click="addCart(index)">添加购物车</button>
      </li>
    </ul>
    <Cart></Cart>
  </div>  

</template>

<script>
import { Cart } from "@/components/Cart"

export default {

  data(){
    return{
      goods:[
        {text:"语文", price:50},
        {text:"数学", price:60},
        {text:"英语", price:70}
      ],
      cart:[]
    }
  },
  methods:{
    onReduce(arg){   
      let {index} = arg
      if (this.cart[index].count > 1) {
        this.cart[index].count -= 1
      }
    },
    onAdd(arg){
      let {index} = arg
      this.cart[index].count += 1
    },
    addCart(i){
      console.log('添加购物车')
      let item = this.goods[i]
      let good = this.cart.find(v => v.text== item.text)
      if(good){
        good.count += 1
      } else {
        this.cart.push({...item, count:1})
      }
    }
    
  },
  components:{
    Cart
  }
  
}
</script>

<style scoped>

</style>