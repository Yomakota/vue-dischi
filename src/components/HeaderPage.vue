<template>
    <header class="header">
        <div class="container-fluid">
            <img class="p-2"
                src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png"
                alt="">
        </div>
    </header>
</template>

<script>
export default {
    name: "HeaderPage"

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