<script>

import { store } from './../store'

export default {
    name: 'reatingStars',
    props: {
        details: Object
    },
    data() {
        return {
            store
        }
    },
    methods: {
        buildVote() {
            // let num = details.vote_average;

            // if (0 <= num < 1.5) {
            //     store.voteStars = 1;
            // } else if (1.5 <= num < 4.5) {
            //     store.voteStars = 2;
            // } else if (1.5 <= num < 4.5) {
            //     store.voteStars = 3;
            // } else if (1.5 <= num < 4.5) {
            //     store.voteStars = 4;
            // } else {
            //     store.voteStars = 5;
            // }
            store.voteStars = 3;
            console.log(store.voteStars);
        }
    },
    created() {
        this.buildVote();
    }
}
</script>

<template>
    <div>
        <!-- (  idx =< voto ) ? piena : vuota -->
        <font-awesome-icon v-for="(element, idx) in 5" class="fa-solid fa-user-secret" />
        <!-- <i class="fa-regular fa-user"></i> icon="fa-solid fa-user-secret"-->
    </div>
</template>

<style lang="scss" scoped></style>
