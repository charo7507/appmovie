


<template>
    <div class="cards">
        <div class="allcards">
            <img :src="movie.Poster" alt="">
        </div>
        <h3 class="movie__name">{{movie.Title}}</h3>
    </div>
</template>

<script setup>

import {defineProps} from 'vue'
defineProps({
    movie: Object
})

</script>

<style lang="scss">
.cards{
    width: 250px;

    .allcards {
        border-radius: .5rem;
        img {
            width: 250px;
            border-radius: .5rem;
        }
    }
}
</style>