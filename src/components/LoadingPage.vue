<template>
    <div
        class="loader-container position-absolute top-0 start-0 d-flex flex-column justify-content-center align-items-center w-100 h-100">
        <div class="loader position-absolute top-50 start-50 translate-middle">
            <div class="hourglass pb-3"></div>
            <div class="text-uppercase">Loading...</div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'LoadingPage',
    data() {
        return {
        }
    }
}
</script>
<style lang="scss" scoped>
@import'../assets/scss/style.scss';

.loader-container {
    background-color: white;

    .loader {
        color: rgb(10, 10, 10);
    }
}
</style>