<template>
    <header class="header d-flex justify-content-between align-items-center ps-3 pe-3">
        <div>
            <img class="p-2" :src='image' :alt="logo_name">
        </div>
        <div>
            <select name="" id="" v-model="valueSelect" @change="$emit('changeGenre', valueSelect)">
                <option value="">
                    Seleziona un genere
                </option>
                <option v-for="(genre, index) in genres" :key="index" :value="genre">
                    {{ genre }}
                </option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "HeaderPage",
    props: ['genres'],
    data() {
        return {
            image: require('../assets/img/Spotify_logo.png'),
            logo_name: 'spotify-logo',
            valueSelect: '',
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
}
</style>