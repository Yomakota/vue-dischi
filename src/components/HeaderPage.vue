<template>
    <header class="header d-flex justify-content-between align-items-center ps-3 pe-3">
        <div>
            <img class="p-2" :src='image' :alt="logo_name">
        </div>
        <div>
            <select class="select border-0 mx-5 text-center" v-model="valueSelect"
                @change="$emit('changeGenre', valueSelect)">
                <option value="">
                    Select genre
                </option>
                <option v-for="(genre, index) in genres" :key="index" :value="genre">
                    {{ genre }}
                </option>
            </select>
            <select class="select border-0 text-center" v-model="selectValueAuthor"
                @change="$emit('changeAuthor', selectValueAuthor)">
                <option value="">
                    Select author
                </option>
                <option v-for="(author, index) in authors" :key="index" :value="author">
                    {{ author }}
                </option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "HeaderPage",
    props: ['genres', 'authors'],
    data() {
        return {
            image: require('../assets/img/Spotify_logo.png'),
            logo_name: 'spotify-logo',
            valueSelect: '',
            selectValueAuthor: '',
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";

.header {
    background-color: $card-color;

    img {
        height: 60px;
    }

    .select {
        background-color: inherit;
        color: white;
        appearance: none;
    }
}
</style>