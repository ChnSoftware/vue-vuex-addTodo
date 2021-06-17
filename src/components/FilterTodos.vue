<template>
    <div class="filter-todos">
        <span>Filter Todos:</span>
        <select @change="filterTodos($event)">
            <option value="200">200</option>
            <option value="100">100</option>
            <option value="50">50</option>
            <option value="20">20</option>
            <option value="10">10</option>
            <option value="5">5</option>
        </select>
    </div>
</template>

<script>
    import { mapActions } from "vuex"

    export default {
        name: "FilterTodos",
        methods: {
            ...mapActions(["filterTodos"])
        }
    }
</script>

<style lang="scss" scoped>
    .filter-todos {
        margin-bottom: 30px;

        select {
            background-color: #242440;
            color: inherit;
            padding: 10px;
            width: 75px;
            font-size: 16px;
            appearance: none;
            // text-align-last: center;
            margin-left: 10px;
            background-image: url("data:image/svg+xml;utf8,<svg fill='white' height='24' viewBox='0 0 24 24' width='24' xmlns='http://www.w3.org/2000/svg'><path d='M7 10l5 5 5-5z'/><path d='M0 0h24v24H0z' fill='none'/></svg>");
            background-repeat: no-repeat;
            background-position-x: 98%;
            background-position-y: 50%;
        }
    }
</style>