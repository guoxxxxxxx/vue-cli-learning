// 组件的结构
<template>
    <div class="school">
        <h2>学校姓名: {{schoolName}}</h2>
        <h2>学校地址: {{schoolAddress}}</h2>
        <button @click="showName">点我提示学校姓名</button>
    </div>
</template>

// 组件交互相关代码
<script>
export default {
    data() {
        return {
            schoolName: 'hebust',
            schoolAddress: 'yx26'
        }
    },
    methods: {
        showName(){
            alert('河北科技大学');
        }
    },
}
</script>

// 组件的样式
<style>
    .school{
        background-color: aqua;
    }
</style>