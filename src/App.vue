<template>
    <div class="container">
        <AddTodo />
        <FilterTodos />
        <Legend />
        <Todos :todos="allTodos" />
    </div>
</template>

<script>
    import Todos from "@/components/Todos"
    import AddTodo from "@/components/AddTodo"
    import FilterTodos from "@/components/FilterTodos"
    import Legend from "@/components/Legend"

    import { mapGetters, mapActions } from "vuex"

    export default {
        name: "App",
        components: { Todos, AddTodo, FilterTodos, Legend },
        created() {
            this.fetchTodos()
        },
        methods: {
            ...mapActions(["fetchTodos"])
        },
        computed: {
            ...mapGetters(["allTodos"])
        }
    }
</script>

<style lang="scss">
    @import url("https://fonts.googleapis.com/css2?family=Mulish:wght@300;400;500&display=swap");

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        border: none;

        &:focus {
            outline: none;
        }
    }

    body {
        font-family: "Mulish", sans-serif;
        line-height: 1.6;
        background-color: #202035;
        color: #bbbbdb;
    }

    .container {
        max-width: 1140px;
        width: 100%;
        margin: auto;
        padding: 2rem;
    }
</style>