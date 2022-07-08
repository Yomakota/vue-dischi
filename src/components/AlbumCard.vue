<template>
    <div class="container-card">
        <div class="card">
            <img class="pb-3" :src="info.poster" :alt="info.title">
            <div class="title pb-3">{{ info.title }}</div>
            <div class="subtitle">{{ info.author }}</div>
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



.card {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: $card-color;
    height: 100%;
    color: white;
    padding: .5em 1em;

    img {
        width: 100%;
    }

    .title {
        text-transform: uppercase;
        text-align: center;
        font-weight: 900;
    }

    .subtitle,
    .date {
        color: grey;
        text-align: center;
        font-size: 12px;
    }
}
</style>