<template>
  <div class="demo">
      <h2>名称: {{name}}</h2>
      <h2>地址: {{address}}</h2>
      <button @click="showInfo">点我显示信息</button>
  </div>
</template>

<script>
// 引入一个混合
import {mixin} from '../mixin.js'
export default {
    name: 'SchoolName',
    data() {
        return {
            name: 'hebust',
            address: 'sjz'
        }
    },
    mixins: [mixin]

}
</script>

<style>
    .demo{
        background-color: aqua;
    }
</style>