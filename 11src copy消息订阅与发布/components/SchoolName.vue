<template>
  <div class="school">
      <h2>名称: {{name}}</h2>
      <h2>地址: {{address}}</h2>
      <button @click="getSchoolName(name)">把学校名给父组件</button>
  </div>
</template>

<script>
import pubsub from 'pubsub-js'
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
    },
    mounted(){
        this.pubId = pubsub.subscribe('hello', function(){
            console.log('有人发布了hello消息, hello消息的回调执行了')
        })
    },
    beforeDestroy(){
        pubsub.unsubscribe(this.pubId);
    }
}
</script>

<style>
    .school{
        background-color: aqua;
    }
</style>