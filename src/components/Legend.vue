<template>
    <div class="legend">
        <span>Double click to mark as complete</span>
        <div class="boxes">
            <span class="incomplete-box"></span>
            <i class="fas fa-exchange-alt"></i>
            Incomplete

            <span class="complete-box"></span>
            <i class="fas fa-exchange-alt"></i>
            Complete
        </div>
    </div>
</template>

<script>
    export default {
        name: "Legend"
    }
</script>

<style lang="scss" scoped>
    .legend {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px;
        background-color: #242440;
        margin-bottom: 30px;

        .boxes {
            display: flex;
            align-items: center;

            .incomplete-box {
                display: inline-block;
                width: 20px;
                height: 20px;
                border-radius: 50%;
                background-color: #dc3545;
            }

            .complete-box {
                display: inline-block;
                width: 20px;
                height: 20px;
                border-radius: 50%;
                background-color: #198754;
                margin-left: 20px;
            }
            i {
                font-size: 12px;
                margin: 0 10px;
            }
        }
    }
</style>