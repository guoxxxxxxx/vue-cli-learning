<template>
  <div class="student">
      <h2>姓名: {{name}}</h2>
      <h2>年龄: {{age+1}}</h2>
      <h2>性别: {{sex}}</h2>
      <button @click="sendStudentName">发送学生姓名给student组件</button>
  </div>
</template>

<script>
export default {
    name: 'StudentInfo',
    data() {
        return {
        }
    },  
    props:{
        name:{
            type: String,
            default:'李亚斌',   // name是否必要
        },
        age:{
            type: Number,
            default: 30,        // 默认值
        },
        sex:{
            type: String,
            default: '男'
        }
    },
    mounted(){
        console.log(this.x); 
    },
    methods:{
        sendStudentName(){
            this.x.$emit('hello', 666);
        }
    }
}
</script>

<style>
.student{
    background-color: aliceblue;
}
</style>