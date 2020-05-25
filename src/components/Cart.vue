<template>
  <div>
      <h2>购物车</h2>

      <table border="1">
          <tr>
              <td>商品</td>
              <td>单价</td>
              <td>价格</td>
              <td>总量</td>
              <td>操作</td>
          </tr>

          <tr v-for="(c,index) in data" :key="c.index">
              <td>{{c.text}}</td>
              <td>{{c.price}}</td>
              <td>{{c.price * c.count}}</td>
              <td>{{c.count}}</td>
              <td>
                  <button @click="add(index)">+</button>
                  <button @click="reduce(index)">-</button>
              </td>
          </tr>
      </table>
  </div>
</template>

<script>
export default{
    name: 'Cart',
    props:['data'],
    methods:{
        add(i){
            this.$emit('add', {index:i})
        },
        reduce(i){
            this.$emit('reduce',{index: i})
        }
    }
}
</script>

<style scoped>

</style>