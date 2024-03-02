<template>
  
    <footer class="footer">
    <!-- This should be `0 items left` by default -->
    <span class="todo-count">还有<strong>{{left}}</strong>条待办</span>
    <!-- Remove this if you don't implement routing -->
    <ul class="filters">
      <li :class="{border:item==current}" v-for="item in indexs" :key="item" @click="$emit('update:current', item)">
        <span class="btn" >{{item}}</span>
      </li>
      
    </ul>
    <!-- Hidden if no completed items are left ↓ -->
    <button class="clear-completed" @click="deleteSelect">删除已完成的事项</button>
  </footer>


 

  
</template>

<script>
export default {
    name: 'ToFooter',
    props:{
        list: [Array],
        current:[String]
    },
    computed:{
        left(){
            return this.list.filter(item=>item.isCheck==false).length
        }
    },
    data() {
        return {
            indexs:['全部','待办','已完成']
        };
    },

    mounted() {
        
    },

    methods: {
        deleteSelect(){
            this.$emit('deleteSelect')
        },
       
    },
};
</script>

<style scoped>

</style>