<template>
    <h3>Todos</h3>
    <div class="todos">
        <Todo v-for="todo in todos" :key="todo.id" :todo="todo" />
    </div>
</template>

<script>
    import Todo from "@/components/Todo"

    export default {
        name: "Todos",
        components: { Todo },
        props: ["todos"],
    }
</script>

<style lang="scss" scoped>
    .todos {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 1rem;

        @media (max-width: 900px) {
            grid-template-columns: 1fr 1fr;
        }
        @media (max-width: 600px) {
            grid-template-columns: 1fr;
        }
    }
</style>