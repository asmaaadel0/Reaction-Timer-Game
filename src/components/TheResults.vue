<template>
    <p>Reaction Time - {{  score  }} ms</p>
    <p class="rank">{{  rank  }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: '',
        }
    },
    mounted() {
        console.log(this.score);
        if (this.score < 250) {
            this.rank = "GREAT JOP!";
        }
        else if (this.score < 400) {
            this.rank = "GOOD JOP!";
        }
        else {
            this.rank = "SLOW...";
        }
    }
}
</script>

<style>
.rank {
    font-size: 1.4rem;
    color: #4fcfd4;
    font-weight: bold;
}
</style>