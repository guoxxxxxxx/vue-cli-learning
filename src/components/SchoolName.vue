<template>
  <div class="school">
      <h2>名称: {{name}}</h2>
      <h2>地址: {{address}}</h2>
      <button @click="getSchoolName(name)">把学校名给父组件</button>
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
    props:{
        getSchoolName:{},
    }
}
</script>

<style>
    .school{
        background-color: aqua;
    }
</style>