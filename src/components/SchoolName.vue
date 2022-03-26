<template>
  <div class="demo">
      <h2>名称: {{name}}</h2>
      <h2>地址: {{address}}</h2>
  </div>
</template>

<script>
export default {
    name: 'SchoolName',
    data() {
        return {
            name: 'hebust',
            address: 'sjz'
        }
    },

}
</script>

<style scoped>
    .demo{
        background-color: aqua;
    }
</style>