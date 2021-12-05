<template>
        <ul  >
           <todo-item  v-for="(item,key) in todos" :key="key"  :item="item" @dblclick="delThis(key)"></todo-item> 
        </ul>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
  components: { TodoItem },
    name:'todo-list',
    props: ['todos'],
    methods:{
      delThis(key) {
        this.$emit('del-this', key)
      }
    }

}
</script>

<style scoped>

</style>