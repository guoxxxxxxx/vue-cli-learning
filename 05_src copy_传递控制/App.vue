<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <header-component :receive="receive" />
        <list-component :todos="todos" :changeStatus='changeStatus'/>
        <footer-component />
      </div>
    </div>
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import ListComponent from "./components/ListComponent.vue";
import FooterComponent from "./components/FooterComponent.vue";
export default {
  name: "App",
  components: {
    HeaderComponent,
    ListComponent,
    FooterComponent,
  },
  data() {
    return {
      todos:[
        {id: '001', title: '吃饭', completed: false},
        {id: '002', title: '睡觉', completed: true},
        {id: '003', title: '学习', completed: false},
      ]
    }
  },
  methods:{
    // 添加一个项目
    receive(x){
      this.todos.push(x);
    },
    // 勾选/取消勾选一个项目
    changeStatus(item){
      item.completed = !item.completed;
    }
  }
};
</script>

<style>
/*base*/
body {
  background: #fff;
}

.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2),
    0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}


</style>