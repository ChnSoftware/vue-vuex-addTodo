<template>
    <div
        class="todo"
        :class="{ 'is-complete': todo.completed }"
        @dblclick="complete(todo)"
    >
        <p>{{ todo.title }}</p>
        <i class="fas fa-times" @click="todoDelete(todo.id)"></i>
    </div>
</template>

<script>
    import { mapActions } from "vuex"

    export default {
        name: "Todo",
        props: ["todo"],
        methods: {
            ...mapActions(["deleteTodo", "updateTodo"]),

            complete(todo) {
                const updatedTodo = {
                    id: todo.id,
                    title: todo.title,
                    completed: !todo.completed
                }
                this.updateTodo(updatedTodo)
            },
            todoDelete(id) {
                this.deleteTodo(id)
            }
        }
    }
</script>

<style lang="scss" scoped>
    .todo {
        background-color: #1b1b30;
        border: 3px solid #dc3545;
        border-radius: 5px;
        cursor: crosshair;
        padding: 1rem;
        text-align: center;
        user-select: none;
        position: relative;
        margin-top: 30px;

        p {
            margin-right: 20px;
            user-select: text;
            text-transform: capitalize;
        }

        i {
            position: absolute;
            top: 10px;
            right: 10px;
            cursor: pointer;
        }
    }
    .is-complete {
        border: 3px solid #198754;
    }
</style>