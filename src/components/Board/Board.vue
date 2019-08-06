<template>
    <div class="board">
        <Cell v-for="_cell in cells" v-bind:cell="_cell"/>
    </div>
</template>

<script>
    import Cell from '../Cells/Abstract';
    import dataCellEnterprises from '../Cells/Enterprises/data';
    import dataCellCorner from '../Cells/Corner/data';
    import dataCellExtra from '../Cells/Extra/data';

    export default {
        name: 'Board',
        data: function () {
            return {
                cells: this.getCells()
            }
        },
        methods: {
            getCells: function () {
                const cellsGroups = [dataCellEnterprises, dataCellCorner, dataCellExtra];
                let mergedCellsGroups = [];

                cellsGroups.forEach(cellsGroup => {
                    cellsGroup.forEach(cell => mergedCellsGroups.push(cell))
                });

                return mergedCellsGroups;
            }
        },
        components: {
            Cell
        }
    }
</script>

<style lang="scss">
    .board {
        min-height: 100vh;
        padding: 20px + 1;
        display: grid;
        grid-template-columns: repeat(9, 1fr);
        grid-template-rows: repeat(9, 1fr);
    }
</style>
