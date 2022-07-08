<template>
    <div>
        <div class="container my-5">
            <div class="row row-cols-5">
                <AlbumCard class="mb-3" v-for=" element, index in albums" :key="index" :info="element" />
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import AlbumCard from './AlbumCard.vue'

export default {
    name: "ListAlbums",
    components: {
        AlbumCard,
    },
    data() {
        return {
            url: "https://flynn.boolean.careers/exercises/api/array/music",
            albums: [],
        }
    },

    created() {
        this.getAlbumCard();
    },

    methods: {
        getAlbumCard() {
            axios.get(this.url).then((result) => {
                this.albums = result.data.response
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
    margin: auto;
}
</style>