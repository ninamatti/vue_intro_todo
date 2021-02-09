<template>
    <div v-for="todo in todos" v-bind:key="todo.id">
        <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" v-on:complete-todo="$emit('complete-todo', todo.id)">{{ todo.title }}</TodoItem>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
    name: "Todos",
    props: ["todos"],
    components: {
        TodoItem
    }
}
</script>

<style scoped>

</style>