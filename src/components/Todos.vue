<template>
    <div>
        <TodoItem />
        <div v-bind:key="todo.id" v-for="todo in todos">
            <h3>{{todo.title}}</h3>
            <TodoItem v-bind:todo="todo" />
        </div>
    </div>    
</template>

<script>
import TodoItem from './TodoItem'
export default {
    name: "Todos",
    component: [
        TodoItem
    ],
    props: ["todos"]
}
</script>

<style scoped>

</style>