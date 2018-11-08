<template>
  <div id="app">
    <input type="text" v-model="todo" @keyup.enter="addItem" class="txt" placeholder="请输入待办事项">
    <input type="button" value="添 加" @click="addItem" class="btn">
    <ul class="list">
      <li
      is="todo-item"
      v-for="(item, index) in items"
      :key="index"
      :content="item"
      @remove="removeItem(index)"></li>
    </ul>
  </div>
</template>

<script>
import TodoList from './components/TodoList'

export default {
  name: 'App',
  data () {
    return {
      todo: '',
      items: []
    }
  },
  components: {
    'todo-item': TodoList
  },
  methods: {
    addItem () {
      this.todo && this.items.push(this.todo)
      this.todo = ''
    },
    removeItem (index) {
      this.items.splice(index, 1)
    }
  }
}
</script>

<style scoped>
  #app {
    width: 1000px;
    margin: 200px auto;
    text-align: center;
  }
  .txt {
    width: 240px;
    height: 40px;
    color: #666;
    padding: 0 10px;
    border: 1px solid #ddd;
    vertical-align: top;
    outline: none;
  }
  .btn {
    width: 100px;
    height: 42px;
    color: #fff;
    background-color: orange;
    border: 1px solid orange;
    outline: none;
    cursor: pointer;
  }
  .list {
    margin-top: 20px;
  }
</style>
