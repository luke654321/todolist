<template>
  <div class="todoapp">
     <to-header @add="add"></to-header>
     <to-body :list="showList" @del="del" @select="select"></to-body>
     <to-footer :current.sync="current" :list="list" @deleteSelect="deleteSelect" ></to-footer>
    
  </div>
</template>

<script>

import '@/assets/index.css'
import ToHeader from '@/components/To-Header.vue'
import ToBody from '@/components/To-Body.vue'
import ToFooter from '@/components/To-Footer.vue'

export default {
  name: 'App',
  computed:{
    showList(){
      if(this.current=='全部' || this.current=='' ){
        return this.list
      }
      if(this.current=='待办'){
        return this.list.filter(item=>item.isCheck==false)
      }
      if(this.current=='已完成'){
        return this.list.filter(item=>item.isCheck==true)
      }
     
    }
  },
  watch:{
    list: {
      handler: function (val) {
        localStorage.setItem('vue-todo', JSON.stringify(val));
      },
      deep: true
    },
  
  },
  data() {
    return {
      current:'',
      list: JSON.parse(localStorage.getItem('vue-todo')) || []
    };
  },
  methods:{
    add(text){
      this.list.push({id:Date.now(),text,isCheck:false})
    },
    del(id){
      this.list=this.list.filter(item=>item.id!=id)
    },
    select(id){
      let item=this.list.find(item=>item.id==id)
      item.isCheck=!item.isCheck
    },
    deleteSelect(){
      this.list=this.list.filter(item=>item.isCheck==false)
    },
   
  },
  components: {
    ToHeader,
    ToBody,
    ToFooter
  }
}
</script>

<style>
#app {
 
}
</style>
