<template>
    <li>
        <div>
            <input
                type="checkbox"
                @change="todo.done = !todo.done"
            >
            <span :class="{done: todo.done}">
                {{todo.text}}
            </span>
        </div>
        <button
            @click="$emit('remove-todo', todo.id)"
        >
            Убрать
        </button>
    </li>
</template>

<script>
    export default {
        name: 'Hello',
        props: {
            todo: Object
        },
    }
</script>

<style scoped>
    input {
        margin-right: 20px;
    }
    .done {
        text-decoration: line-through;
    }
</style>
