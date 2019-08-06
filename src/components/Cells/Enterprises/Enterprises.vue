<template>
    <div :class="getCellCssClass" class="cell">
        <div class="cell-name">{{cell.data.groupName + '-' + cell.data.index}}</div>
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
                    this.cell.data.groupName,
                    'cell' + this.cell.data.index
                ];
            }
        }
    }
</script>

<style lang="scss">
    .board {
        .cell {
            // colors
            &.group1 {
                background-color: #2196f3;
            }

            &.group2 {
                background-color: #ff9800;
            }

            &.group3 {
                background-color: #8bc34a;
            }

            &.group4 {
                background-color: #607d8b;
            }

            &.group5 {
                background-color: #795548;
            }

            &.group6 {
                background-color: #009688;
            }

            &.group7 {
                background-color: #673ab7;
            }

            &.group8 {
                background-color: #f44336;
            }

            // layout
            &.group3 {
                grid-column: 11;
            }

            &.group4 {
                grid-column: 11;
            }

            &.group5 {
                grid-row: 11;

                &.cell1 {
                    grid-column: 10;
                }

                &.cell2 {
                    grid-column: 8;
                }

                &.cell3 {
                    grid-column: 7;
                }
            }

            &.group6 {
                grid-row: 11;

                &.cell1 {
                    grid-column: 2;
                }

                &.cell2 {
                    grid-column: 3;
                }

                &.cell3 {
                    grid-column: 5;
                }
            }

            &.group7 {
                grid-column: 1;

                &.cell1 {
                    grid-row: 2;
                }

                &.cell2 {
                    grid-row: 3;
                }

                &.cell3 {
                    grid-row: 5;
                }
            }

            &.group8 {
                grid-column: 1;

                &.cell1 {
                    grid-row: 10;
                }

                &.cell2 {
                    grid-row: 8;
                }

                &.cell3 {
                    grid-row: 7;
                }
            }

        }
    }
</style>