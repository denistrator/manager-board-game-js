<template>
    <div :class="getCellCssClass" class="cell">
        <div class="cell-name">{{cell.data.displayName}}</div>
    </div>
</template>

<script>
    export default {
        name: 'cellCorner',
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
            &.corner {
                &.start {
                    grid-row: 1;
                    grid-column: 1;
                }

                &.exchange {
                    grid-row: 1;
                    grid-column: 11;
                }

                &.broker {
                    grid-row: 11;
                    grid-column: 1;
                }

                &.rest {
                    grid-row: 11;
                    grid-column: 11;
                }

            }
        }
    }

</style>