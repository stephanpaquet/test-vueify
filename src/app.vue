<style>
    .red {
        color: #f00;
        }
</style>

<template>
    <h2 class="red">{{ msg }}</h2>
</template>

<script>
module.exports = {
    props: ['msg'],
    data: function () {
        return {
            msg: 'Hello world!'
        }
    }
}
</script>
