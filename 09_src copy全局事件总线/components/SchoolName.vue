<template>
  <div class="school">
      <h2>名称: {{name}}</h2>
      <h2>地址: {{address}}</h2>
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
    mounted(){
        console.log('school', this.x);
        this.x.$on('hello',(data)=>{
            console.log('receive:', data);
        })
    },
    beforeDestroy(){
        this.$bus.$off('hello')
    }
}
</script>

<style>
    .school{
        background-color: aqua;
    }
</style>