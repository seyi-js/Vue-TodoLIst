<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.Completed}">
        
        <p>
            <input type="checkbox" v-on:change="markComplete"/>
            {{todo.Title}}
            <button @click="$emit('del-todo', todo.ID)" class="del">x</button>
        </p>  
    </div>
</template>




<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(){
            this.todo.Completed = !this.todo.Completed
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del{
        background: #89f789;
        color: #fff;
        border: none;
        float: right;
        padding: 5px;
    }
</style>
