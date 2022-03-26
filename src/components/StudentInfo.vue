<template>
  <div class="s">
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
        }
    },
    // 简单声明接收
    // props:['name', 'age', 'sex']
    
    // 接收的同时对数据进行类型限制
    // props:{
    //     name: String,
    //     age: Number,
    //     sex: String,
    // }

    //  
    props:{
        name:{
            type: String,
            require:true,   // name是否必要
        },
        age:{
            type: Number,
            default: 30,        // 默认值
        },
        sex:{
            type: String,
            require: true
        }
    }
}
</script>

<style>
.s{
    background-color: aliceblue;
}
</style>