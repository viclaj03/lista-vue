<template>
        <form>
            <button v-on:click.prevent="deleteAll" >Borrar todo</button>
        </form>
</template>

<script>
export default {
    name:'delete-todo',
    methods:{
    deleteAll(){
           if(confirm('Deseas borrar toda la lista')){
               this.$emit('delete-all')
           }
        }
    }
}

</script>

<style scoped>

</style>