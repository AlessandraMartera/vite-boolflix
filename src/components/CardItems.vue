<script>
import { store } from './../store'
import ratingsStars from './ratingsStars.vue'

export default {
    name: 'CardItems',
    components: {
        ratingsStars
    },
    props: {
        details: Object
    },
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <li>
        <div>
            <img :src="`${store.thumbImg}${details.backdrop_path}`" :alt="`motion picture ${details.title}${details.name}`">
        </div>

        <div v-if="(store.movieList.includes(details))">
            <!-- title -->
            <div>
                {{ details.title }}
            </div>

            <!-- original title -->
            <div>
                {{ details.original_title }}
            </div>
        </div>

        <div v-else-if="(store.tvList.includes(details))">
            <!-- name -->
            <div>
                {{ details.name }}
            </div>

            <!-- original name -->
            <div>
                {{ details.original_name }}
            </div>
        </div>

        <!-- language -->
        <div class="language">
            <img :src="`language/${details.original_language}.jpg`" :alt="`${details.original_language} language`">

        </div>

        <!-- vote -->
        <div class="ratings">
            <ratingsStars v-for="(n, idx) in 5" :vote="details.vote_average" :pos="idx" />
        </div>

    </li>
</template>

<style lang="scss" scoped>
.language {
    width: 50px;
    height: 30px;

    img {
        width: 100%;
        height: 100%;
    }
}

.hidden {
    display: none;
}

.active {
    display: block;
}
</style>