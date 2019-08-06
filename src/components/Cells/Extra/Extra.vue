<template>
    <div :class="getCellCssClass" class="cell">
        <div class="cell-name">{{cell.data.displayName}}</div>
    </div>
</template>

<script>
    export default {
        name: 'cellExtra',
        props: [
            'cell'
        ],
        computed: {
            getCellCssClass() {
                return [
                    this.cell.category,
                    this.cell.data.type,
                    this.cell.data.type + '-' + this.cell.data.index
                ];
            }
        }
    }
</script>

<style lang="scss">
    .board {
        .cell {
            &.gift-1,
            &.surprise-1,
            &.notice-1 {
                grid-row: 1;
            }

            &.gift-1 {
                grid-column: 4;
            }

            &.surprise-1 {
                grid-column: 6;
            }

            &.notice-1 {
                grid-column: 9;
            }

            &.gift-2,
            &.surprise-2,
            &.notice-2 {
                grid-column: 11;
            }

            &.gift-2 {
                grid-row: 4;
            }

            &.surprise-2 {
                grid-row: 6;
            }

            &.notice-2 {
                grid-row: 9;
            }

            &.gift-3,
            &.surprise-3,
            &.notice-3 {
                grid-row: 11;
            }

            &.gift-3 {
                grid-column: 9;
            }

            &.surprise-3 {
                grid-column: 6;
            }

            &.notice-3 {
                grid-column: 4;
            }

            &.gift-4,
            &.surprise-4,
            &.notice-4 {
                grid-column: 1;
            }

            &.gift-4 {
                grid-row: 9;
            }

            &.surprise-4 {
                grid-row: 6;
            }

            &.notice-4 {
                grid-row: 4;
            }
        }
    }
</style>
