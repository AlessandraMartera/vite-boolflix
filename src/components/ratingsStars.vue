<script>

import { store } from './../store'

export default {
    name: 'reatingStars',

    props: ['vote', 'pos'],

    data() {
        return {
            store
        }
    },
    methods: {
        buildVote() {

            // store.voteStars

            // num = parseFloat(this.voteTen) / 2;
            // console.log(`num is ${num}`);

            // if (num >= 4.5) {
            //     // console.log('5');
            //     num = 5;
            // } else if (num >= 3.5) {
            //     // console.log('4');
            //     num = 4;
            // } else if (num >= 2.5) {
            //     // console.log('3');
            //     num = 3;
            // } else if (num >= 1.5) {
            //     // console.log('2');
            //     num = 2;
            // } else if (num >= 0.5) {
            //     // console.log('1');
            //     num = 1;
            // } else {
            //     // console.log('0');
            //     num = 0;
            // }

            // console.log(store.voteStars);
        }
    },
    created() {
        // this.buildVote(num);
    }
}
</script>

<template>
    <!-- {{ Math.ceil(vote / 2) }} -->
    <i :class="(pos) < Math.ceil(vote / 2) ? 'fa-solid fa-star' : 'fa-regular fa-star'"></i>
    <!-- (  idx =< voto ) ? piena : vuota -->
    <!-- (  idx =< voto ) ? 'fa-solid fa-star' : 'fa-regular fa-star' -->
    <!-- <i class="fa-solid fa-star"></i>  -->
</template>

<style lang="scss" scoped></style>
