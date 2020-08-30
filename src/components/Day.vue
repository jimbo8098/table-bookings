<template>
    <div class="day">
        {{ ordinal }}
    </div>
</template>

<script>
export default {
    name: 'day',
    props: {
        ordinal: Number
    }
}
</script>

<style scoped>
    .day {
        background-color: cornflowerblue;
        border: 1px solid red;
        margin: 2px;
        padding: 2px;
        width: 30px;
    }
</style>