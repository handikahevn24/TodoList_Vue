<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo',todo.id)"/>
        </div>   
    </div>    
</template>


<script>
import TodoItem from './TodoItem.vue'; //import Component Todo item 
export default {
    name: "Todos", // Nama Komponen
    components: {
        TodoItem // Menambahkan Komponen Hasil Import
    },
    props: ["todos"] //Tambah Props todos untuk menyimpan Value
}
</script>


<style scoped>

</style>
