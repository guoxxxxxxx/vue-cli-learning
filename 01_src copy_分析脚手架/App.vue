<template>
  <div>
      <img src="./assets/logo.png" alt="logo">
      <School></School>
      <Student></Student>
  </div>
</template>

<script>
    // 引入组件
    import School from './components/SchoolInfo.vue'
    import Student from './components/StudentInfo.vue'
    export default {
        name: 'App',
        components:{
            School,
            Student
        }
    }
</script>

<style>

</style>