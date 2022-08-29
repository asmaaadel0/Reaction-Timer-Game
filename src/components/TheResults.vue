<template>
    <p v-if="showResult">Reaction Time - {{  score  }} ms</p>
    <p v-if="showResult" class="rank">{{  rank  }}</p>
</template>

<script>
export default {
    props: ['showResult', "score"],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
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