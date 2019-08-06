<template>
    <CellCorner v-if="isCorner" v-bind:cell="cell"/>
    <CellEnterprises v-else-if="isEnterprise" v-bind:cell="cell"/>
    <CellExtra v-else-if="isExtra" v-bind:cell="cell"/>
</template>

<script>
    import CellCorner from './Corner/Corner';
    import CellEnterprises from './Enterprises/Enterprises';
    import CellExtra from './Extra/Extra';

    export default {
        name: 'Cell',
        data: function () {
            return {}
        },
        props: [
            'cell'
        ],
        methods: {
            getIsCellCategoryTypeOf: function (category) {
                return this.cell.category.includes(category)
            }
        },
        computed: {
            isCorner() {
                return this.getIsCellCategoryTypeOf('corner');
            },
            isEnterprise() {
                return this.getIsCellCategoryTypeOf('enterprise');
            },
            isExtra() {
                return this.getIsCellCategoryTypeOf('extra');
            }
        },
        components: {
            CellCorner,
            CellEnterprises,
            CellExtra
        }
    }
</script>

<style lang="scss">
    .board {
        .cell {
            margin: -1px;
            padding: 20px;
            border: 2px solid #222;
        }
    }
</style>
