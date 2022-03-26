<template>
  <div class="s">
      <h2>姓名: {{name}}</h2>
      <h2>年龄: {{age+1}}</h2>
      <h2>性别: {{sex}}</h2>
      <button @click="showInfo">点击显示信息</button>
  </div>
</template>

<script>
// 引入一个混合
import {mixin} from '../mixin.js'
export default {
    name: 'StudentInfo',
    data() {
        return {
            name: 'Jack',
            age: 18,
            sex: '男'
        }
    },
    mixins: [mixin]

}
</script>

<style>
.s{
    background-color: aliceblue;
}
</style>