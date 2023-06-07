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
            {{ cardMovie.title }}
        </li>

    </ul>

    <h1>SerieTv:</h1>
    <ul>
        <li v-for="cardTv in store.cardListTv">
            {{ cardTv.name }}
        </li>

    </ul>
</template>

<style lang="scss" scoped></style>