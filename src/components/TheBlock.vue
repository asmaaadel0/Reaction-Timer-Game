<template>
    <div class="block" v-if="showBlock">Click Me!</div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
        }, this.delay)

    },
    updated() {

    }
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
    color: white;
    font-weight: 600;
    font-size: 1.6rem;
}
</style>