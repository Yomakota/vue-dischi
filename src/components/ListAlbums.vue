<template>
    <section id="main-content">
        <div class="container my-5">
            <div class="row row-cols-5" v-if="isLoaded">
                <AlbumCard class="mb-3" v-for=" element, index in albums" :key="index" :info="element" />
            </div>
            <LoadingPage v-else />
        </div>
    </section>
</template>

<script>
import axios from 'axios';
import AlbumCard from './AlbumCard.vue'
import LoadingPage from './LoadingPage.vue'

export default {
    name: "ListAlbums",
    components: {
        AlbumCard,
        LoadingPage,
    },
    data() {
        return {
            url: "https://flynn.boolean.careers/exercises/api/array/music",
            albums: [],
            isLoaded: false
        }
    },

    mounted() {
        setTimeout(() => {
            this.getAlbumCard();
        }, 2000);
    },

    methods: {
        getAlbumCard() {
            axios.get(this.url).then((result) => {
                this.albums = result.data.response;
                this.isLoaded = true;
            })
                .catch((err) => {
                    console.log("Error", err);
                });
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";

.container {
    width: 60%;
}
</style>