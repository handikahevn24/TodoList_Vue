<template>
    <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markCompleted">
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)"
             class="del">X</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        async markCompleted(){
            this.todo.completed = !this.todo.completed;
        }
    }    
}
</script>


<style scoped>
    .todo-item {
        background: #fafafa;
        padding: 10px;
        border-bottom: #ccc dotted;
    }

    .is-completed {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #ffffff;
        border: none;
        padding: 5px 9px;
        border-radius: 30%;
        cursor: pointer;
        float: right;
        
    }
</style>
