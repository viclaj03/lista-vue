<template>
        <li> 
            <input type="checkbox" :checked=item.done  @click="changeDone">
            <span v-if="!item.done"> {{item.title}}  </span>
            <del v-else>{{item.title}} </del> 
        </li>
</template>

<script>
export default {
    name:'todo-item',
    props: [ 'key','item'],
    methods:{
        changeDone(){
            this.$emit('change-this')
        }
    }
}

</script>

