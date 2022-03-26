<template>
  <ul class="todo-main">
    <item-component v-for="(item) in todos" :key="item.id" :item="item"/>
  </ul>
</template>

<script>
import ItemComponent from "./ItemComponent.vue";
export default {
  name: "ListComponent",
  components: {
    ItemComponent
  },
  props:{
    todos:{
      
    }
  }
};
</script>

<style scoped>
/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>