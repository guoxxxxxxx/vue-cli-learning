<template>
  <div class="todo-footer" v-if="todos.length">
    <label>
      <input type="checkbox" :checked='isAll' @click="changeAllButton(isAll)"/>
    </label>
    <span> <span>已完成{{doneTotal}}</span> / 全部{{todos.length}} </span>
    <button class="btn btn-danger" @click="clearAchieve">清除已完成任务</button>
  </div>
</template>

<script scoped>
export default {
  name: "FooterComponent",
  props:{
    todos:{},
    clearAchieve:{},
    selectAllItem:{},
  },
  computed:{
    doneTotal(){
      let count = 0;
      this.todos.forEach(element => {
        if(element.completed === true){
          count++
        }
      });
      return count;
    },
    isAll(){
      return this.doneTotal === this.todos.length && this.todos.length > 0;
    }
  },
  methods:{
    changeAllButton(isAll){
      this.selectAllItem(isAll);
    }
  }
};
</script>

<style>/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>