<template>
    <div class="todo-item" v-bind:class="{'is-complete': todo.completed }">
        <p>{{todo.title}}</p>
        <input type="checkbox" v-bind:checked="todo.completed" v-on:change="markComplete">
        <button @click="$emit('del-todo', todo.id)" class="del">X</button>
    </div>
</template>

<script>
    export default {
        name: 'TodoItem',
        props: ['todo'],
        methods: {
            markComplete() {
               this.todo.completed = !this.todo.completed
            }
        },
    }
</script>

<style scoped>

    .is-complete {
        text-decoration: line-through;
    }

</style>