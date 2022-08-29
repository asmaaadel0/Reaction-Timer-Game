<template>
    <div class="block">Click Me!</div>
</template>

<script>
export default {
    props: ['delay'],
}
</script>

<style>
.block {
    background-color: rgba(86, 32, 109, 0.611);
    width: 25rem;
    height: 8rem;
    border-radius: 2rem;
    text-align: center;
    padding-top: 6rem;
    margin: 4rem auto;
}
</style>