<template>
    <li class="item" @click="handleClick">{{value}}</li>
</template>

<script>
export default {
    props: ['index', 'value'],
    methods: {
        handleClick: function () {
            this.$emit('delete', this.index)
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .item {
        color: green;
    }
</style>
