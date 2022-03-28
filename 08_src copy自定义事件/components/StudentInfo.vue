<template>
  <div class="student">
      <h2>姓名: {{name}}</h2>
      <h2>年龄: {{age+1}}</h2>
      <h2>性别: {{sex}}</h2>
      <button @click="sendStudentName">点我发送学生姓名</button>
      <button @click="unbind">解绑自定义事件</button>
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
    methods: {
        sendStudentName(){
            // 触发Student组件实例身上的硅谷事件 
            this.$emit('atguigu', this.name)
        },
        unbind(){
            this.$off('atguigu')    // 解绑一个自定义事件
            // 解绑多个事件
            this.$off(['event1', 'event2'])
            // 解绑所有自定义事件
            this.$off()
        }
    },
}
</script>

<style>
.student{
    background-color: aliceblue;
}
</style>