<template>
    <div id="albums">
        <div class="album d-flex flex-column align-items-center h-100 p-3">
            <img class="w-100 pb-3" :src="info.poster" :alt="info.title">
            <div class="title text-uppercase text-center fw-bold pb-3">{{ info.title }}</div>
            <div class="subtitle text-center">{{ info.author }}</div>
            <div class="date">{{ info.year }}</div>
        </div>
    </div>
</template>

<script>
export default {
    name: "AlbumCard",
    props: ['info']
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";

.album {
    background-color: $card-color;

    .subtitle,
    .date {
        color: grey;
        font-size: 12px;
    }
}
</style>