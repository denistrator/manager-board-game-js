<template>
    <Board/>
</template>

<script lang="ts">
    import Board from './components/Board/Board.vue';

    export default {
        name: "Manager",
        components: {
            Board
        }
    };
</script>

<style lang="scss">
    @import 'app.scss';
</style>
