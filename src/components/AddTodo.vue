<template>
    <form
        @submit.prevent="addTask"
    >
        <input
            type="text"
            placeholder="Новое дело"
            v-model="text"
        >
        <button
            type="submit"
        >
            Добавить
        </button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                text: ''
            }
        },
        methods: {
            addTask() {
                if(this.text.trim) {
                    const newTask = {
                        id: Date.now,
                        text: this.text,
                        done: false
                    }
                    this.$emit('add-task', newTask)
                    this.text = ''
                }
            }
        }
    }
</script>
