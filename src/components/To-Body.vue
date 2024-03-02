<template>
  <section class="main">
    <input id="toggle-all" class="toggle-all" type="checkbox" />
    <label for="toggle-all">Mark all as complete</label>
    <ul class="todo-list">
      <li  :class="{completed:item.isCheck}" v-for="item in list" :key="item.id">
        <div class="view">
          <input class="toggle" type="checkbox" :checked="item.isCheck" @click="select(item.id)"/>
          <label>{{item.text}}</label>
          <button class="destroy" @click="del(item.id)"></button>
        </div>
        <input class="edit" value="Create a TodoMVC template" />
      </li>
    
      
    </ul>
  </section>
</template>

<script>
export default {
  name: 'ToBody',
  props: {
    list: [Array],
  },

  data() {
    return {}
  },

  mounted() {},

  methods: {
    del(id){
        this.$emit('del',id)
    },
    select(id){
      this.$emit("select",id)
    }
  },
}
</script>

<style scoped></style>
