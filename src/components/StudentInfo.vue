<template>
  <div class="demo">
      <h2>姓名: {{name}}</h2>
      <h2>年龄: {{age+1}}</h2>
      <h2>性别: {{sex}}</h2>
  </div>
</template>

<script>
export default {
    name: 'StudentInfo',
    data() {
        return {
            name: 'Jack',
            age: 18,
            sex: '男'
        }
    },

}
</script>

<style scoped>
.demo{
    background-color: aliceblue;
}
</style>