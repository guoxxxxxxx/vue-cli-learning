<template>
  <div class="app">
    <h1>{{msg}}</h1>
    <!-- 通过父组件给子组件传递函数类型的props实现: 子给父传递数据 -->
    <school-name :getSchoolName='getSchoolName'/>
    <!-- 通过父组件给子组件绑定一个自定义事件实例:子给父传递数据 -->
    <!-- <student-info v-on:atguigu='demo'/> -->
    <!-- 通过父组件给子组件绑定一个自定义事件实例:子给父传递数据 第二种写法 -->
    <student-info ref='student'/>
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
   methods: {
     getSchoolName(name){
       console.log("App收到了学校名:", name);
     },
     demo(name){
       console.log('demo被调用了' + name);
     }
   },
   mounted() {
     this.$refs.student.$on('atguigu', this.demo);
   },
};
</script>

<style>
.app{
  background-color: yellowgreen;
}
</style>