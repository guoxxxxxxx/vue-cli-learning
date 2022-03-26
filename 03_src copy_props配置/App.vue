<template>
  <div id="root">
    <SchoolName></SchoolName>
    <StudentInfo name="李四" sex="男" :age='20'></StudentInfo>
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
};
</script>

<style>
</style>