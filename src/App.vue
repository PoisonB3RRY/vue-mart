<template>
  <div>
    <el-container>
      <el-header>
        <el-menu mode="horizontal">
          <el-menu-item index="1">
            <img width="100px"
                 src="https://img.kaikeba.com/logo-new@2x.png"
                 alt="">
          </el-menu-item>
          <el-menu-item index="2">
            <router-link to="/">首页</router-link>
          </el-menu-item>
          <el-menu-item index="3"
                        style="float:right;">
            <router-link to="/cart">
              <i class="el-icon-shopping-cart-2"></i>
            </router-link>
          </el-menu-item>
        </el-menu>
      </el-header>
      <el-main>
        <!-- 切换页面内容渲染 -->
        <router-view></router-view>
      </el-main>
    </el-container>
  </div>

</template>

<script>
import Vue from 'vue';
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';

// import axios from 'axios'

Vue.use(ElementUI)

export default {

  data () {
    return {
      title: 'Fake TAOBAO'
    }
  },
  methods: {
    addCart (i) {
      console.log('添加购物车' + i)
      let item = this.goods[i]
      let good = this.cart.find(v => v.text == item.text)
      console.log(good)
      if (good) {
        good.count += 1
      } else {
        this.cart.push({ ...item, count: 1 })
      }
    }

  }

}
</script>

<style scoped>
.button {
  width: 100%;
}
</style>