<template>
    <div class="add-todo">
        <h3>Add Todo</h3>
        <form @submit.prevent="addNewTodo">
            <input type="text" placeholder="Add Todo" v-model="title" />
            <input type="submit" value="Submit" />
        </form>
    </div>
</template>

<script>
    import { mapActions } from "vuex"

    export default {
        name: "AddTodo",
        data() {
            return {
                title: ""
            }
        },
        methods: {
            ...mapActions(["addTodo"]),

            addNewTodo() {
                if (this.title.trim()) {
                    this.addTodo(this.title)
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    .add-todo {
        margin-bottom: 30px;

        h3 {
            margin-bottom: 30px;
        }

        form {
            display: flex;
            align-items: center;

            input {
                background-color: #1b1b30;
                color: inherit;
                font-size: 20px;
                padding: 20px;
            }
            input[type="text"] {
                flex: 5;
                background-color: lighten(#1b1b30, 5%);
            }
            input[type="submit"] {
                flex: 1;
                cursor: pointer;
                transition: 300ms transform ease;

                &:active {
                    transform: scale(0.9);
                }
            }
        }
    }
</style>