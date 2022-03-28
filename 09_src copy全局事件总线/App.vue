<template>
  <div class="app">
    <h1>{{msg}}</h1>
    <school-name/>
    <student-info/>
  </div>
</template>

<script>
// 引入school组件
import SchoolName from "./components/SchoolName.vue";
import StudentInfo from "./components/StudentInfo.vue"
export default {
  components: { 
      SchoolName,
      StudentInfo,
   },
   data() {
     return {
       msg:"this is a msg!"
     }
   },
};
</script>

<style>
.app{
  background-color: yellowgreen;
}
</style>