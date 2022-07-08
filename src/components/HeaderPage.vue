<template>
    <header class="header">
        <div class="container-fluid">
            <img class="p-2" :src='url' :alt="logo_name">
        </div>
    </header>
</template>

<script>
export default {
    name: "HeaderPage",
    data() {
        return {
            url: 'https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png',
            logo_name: 'spotify-logo'
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