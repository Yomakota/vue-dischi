<template>
    <section id="main-content">
        <div class="container w-75 my-5">
            <div class="row row-cols-5" v-if="isLoaded">
                <AlbumCard class="mb-3" v-for=" element, index in filterAlbum" :key="index" :info="element" />
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
    props: ['genre'],
    data() {
        return {
            url: "https://flynn.boolean.careers/exercises/api/array/music",
            albums: [],
            genres: [],
            isLoaded: false
        }
    },
    computed: {
        filterAlbum() {
            if (this.genre === '') {
                return this.albums;
            }
            return this.albums.filter((element) => element.genre === this.genre)
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

                this.albums.forEach((element) => {
                    if (!this.genres.includes(element.genre)) {
                        this.genres.push(element.genre);
                    }
                });
                this.$emit('genresStart', this.genres);
            })
                .catch((err) => {
                    console.log("Error", err);
                });
        },
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
</style>