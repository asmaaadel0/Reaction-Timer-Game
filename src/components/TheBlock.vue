<template>
    <transition name="box">
        <div class="block" v-if="showBlock" @click="stopTimer">Click Me!</div>
    </transition>
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

.box-enter-from,
.box-leave-to {
    opacity: 0;
    transform: scale(0.8);
}

.box-enter-active {
    transition: all 0.3s ease-out;
}

.box-leave-to {
    transition: all 0.3s ease-in;
}

.box-enter-to,
.box-leave-form {
    opacity: 1;
    transform: scale(1);
}
</style>