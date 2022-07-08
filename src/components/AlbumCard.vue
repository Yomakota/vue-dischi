<template>
    <div>
        <div class="card mb-2">
            <img class="pb-3" :src="info.poster" :alt="info.title">
            <div class="title pb-1">{{info.title}}</div>
            <div class="subtitle">{{info.author}}</div>
            <div class="date">{{info.year}}</div>
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
.card {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: $card-color;
    height: 100%;

    img {
        width: 100%;
    }

    .title {
        text-transform: uppercase;
        color: white;
        font-weight: 500;
        text-align: center;
    }

    .subtitle, 
    .date {
        color: grey;
    }
}
</style>