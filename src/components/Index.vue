<template>
  <div>
    <section class="todoapp">
  <header class="header">
    <h1>TodoMVC • Static</h1>
    <input class="new-todo" placeholder="请输入待办事项并按回车键" autofocus>
  </header>
  <!-- This section should be hidden by default and shown when there are todos -->
  <section class="main">
    <input id="toggle-all" class="toggle-all" type="checkbox">
    <label for="toggle-all">Mark all as complete</label>
    <ul class="todo-list">
      <!-- These are here just to show the structure of the list items -->
      <!-- List items should get the class `editing` when editing and `completed` when marked as completed -->
      <li class="completed">
        <div class="view">
          <input class="toggle" type="checkbox" checked>
          <label>Taste JavaScript</label>
          <button class="destroy"></button>
        </div>
        <input class="edit" value="Create a TodoMVC template">
      </li>
      <li>
        <div class="view">
          <input class="toggle" type="checkbox">
          <label>Buy a unicorn</label>
          <button class="destroy"></button>
        </div>
        <input class="edit" value="Rule the web">
      </li>
    </ul>
  </section>
  <!-- This footer should be hidden by default and shown when there are todos -->
  <footer class="footer">
    <!-- This should be `0 items left` by default -->
    <span class="todo-count">还有<strong>0</strong>条待办</span>
    <!-- Remove this if you don't implement routing -->
    <ul class="filters">
      <li>
        <span class="btn">全部</span>
      </li>
      <li>
        <span class="btn">待办</span>
      </li>
      <li>
        <span class="btn">已完成</span>
      </li>
    </ul>
    <!-- Hidden if no completed items are left ↓ -->
    <button class="clear-completed">删除已完成的事项</button>
  </footer>
</section>
<footer class="info">
  <p>点击左上角下拉箭头，可全部标记为已完成。</p>
  <p>鼠标双击事项文本，会激活输入框，可进行修改文本内容。</p>
  <p>当输入框激活时，可以按 esc 退出，不保存输入的内容。</p>
  <p>输入框失去焦点/按回车 则自动保存新文本。</p>
  <p>如果在输入框中清除了所有文本，则自动删除这条待办事项</p>
</footer>
  </div>
</template>

<script>
import '../assets/index.css'
export default {
  name: 'TodolistIndex',

  data() {
    return {}
  },

  mounted() {},

  methods: {},
}
</script>

<style scoped>

</style>
