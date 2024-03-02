<template>
    
        <header class="header">
    <h1>TodoMVC </h1>
    <input @keyup.enter="add" v-model="addText" class="new-todo" placeholder="请输入待办事项并按回车键" autofocus>
  </header>
    
</template>

<script>
export default {
    name: 'ToHeader',

    data() {
        return {
            addText:''
        };
    },

    methods: {
        add(){
            if(this.addText.length==0){
                alert('必填')
                return 
            }
            this.$emit('add', this.addText);
            this.addText=''
        }
    },
};
</script>

<style scoped>

</style>