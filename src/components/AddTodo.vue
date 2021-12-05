<template>
        <form >
            <input type="text" v-model="newTodo">
            <br>
            <button v-on:click.prevent="addTodo">Añadir</button>
        </form>
</template>

<script>
export default {
    name:'add-todo',
    data(){
        return {
            newTodo:''
        }
    },
    methods: {
        addTodo(){
            if(this.newTodo){
                this.$emit('add-list',this.newTodo)
                this.newTodo=''
            }
            
        }
    }   
}

</script>

<style scoped>

</style>