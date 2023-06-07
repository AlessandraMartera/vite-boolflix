<script>
import { store } from './../store';
export default {
    name: 'CardList',
    data() {
        return { store }
    }
}
</script>

<template>
    <h1>Movie:</h1>
    <ul>
        <li v-for="cardMovie in store.cardListMovie">
            <!-- title -->
            <div>
                {{ cardMovie.title }}
            </div>

            <!-- original title -->
            <div>
                {{ cardMovie.original_title }}
            </div>

            <!-- lenguage -->
            <div>
                {{ cardMovie.original_language }}
            </div>

            <!-- vote -->
            <div>
                {{ cardMovie.vote_average }}
            </div>


        </li>

    </ul>

    <h1>SerieTv:</h1>
    <ul>
        <li v-for="cardTv in store.cardListTv">
            <!-- title -->
            <div>
                {{ cardTv.name }}
            </div>

            <!-- original title -->
            <div>
                {{ cardTv.original_name }}
            </div>

            <!-- lenguage -->
            <div>
                {{ cardTv.original_language }}
            </div>

            <!-- vote -->
            <div>
                {{ cardTv.vote_average }}
            </div>
        </li>

    </ul>
</template>

<style lang="scss" scoped></style>