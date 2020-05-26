<template>
  <div>
    <el-row>
      <el-col :span="6"
              v-for="item in goods"
              :key="item.index">
        <el-card>
          <img :src="item.img"
               class="image"
               alt="">
          <div style="padding:14px;">
            <span>{{item.title}}</span>
            <el-button type="text"
                       class="button">
              <i class="el-icon-circle-plus"></i>
            </el-button>
          </div>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
// import axios from 'axios'
export default {

}
</script>

<style>
</style>