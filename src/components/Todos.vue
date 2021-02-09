<template>
    <div v-for="todo in todos" v-bind:key="todo.id">
        <TodoItem v-bind:todo="todo">{{ todo.title }}</TodoItem>
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