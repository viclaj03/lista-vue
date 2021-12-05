<template>
        <li> 
            <input type="checkbox" v-model="item.done" >
            <span v-if="!item.done"> {{item.title}}  </span>
            <del v-else>{{item.title}}</del> 
        </li>
</template>

<script>
export default {
    name:'todo-item',
    props: ['item']
}

</script>

