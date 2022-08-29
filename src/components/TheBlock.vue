<template>
    <div class="block" v-if="showBlock" @click="stopTimer">Click Me!</div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0,
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
        }, this.delay)

    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10;
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer);
            this.$emit("end", this.reactionTime);
        }
    }
}
</script>

<style>
.block {
    background-color: #024144;
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