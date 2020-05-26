<template>
  <div>
    <h2>FAKE Taobao</h2>
    <CartInfo :data='cart'
              :add='onAdd'
              :reduce='onReduce'></CartInfo>
  </div>

</template>

<script>
import CartInfo from "@/components/Cart"

export default {
  components: { CartInfo },

  data () {
    return {
      cart: []
    }
  },
  methods: {
    onReduce (arg) {
      let { index } = arg
      if (this.cart[index].count > 1) {
        this.cart[index].count -= 1
      }
    },
    onAdd (arg) {
      let { index } = arg
      this.cart[index].count += 1
    },
  }

}
</script>

<style>
</style>