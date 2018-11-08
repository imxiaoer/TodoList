<template>
  <li class="todo-item">
    {{content}}
    <input type="button" class="btn-del" value="删除" @click="$emit('remove')">
  </li>
</template>

<script>
export default {
  props: ['content']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .todo-item {
    list-style: none;
    padding-left: 10px;
    margin-top: 10px;
    line-height: 40px;
    color: #333;
    background-color: #f5f5f5;
    text-align: left;
  }
  .btn-del{
    float: right;
    margin: 5px 10px 0 0;
    padding: 5px 10px;
    background-color: #fff;
    border: 1px solid red;
    color: red;
    cursor: pointer;
  }
</style>
