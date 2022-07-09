<template>
    <div class="loader-container">
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
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background-color: white;

    .loader {
        color: rgb(10, 10, 10);
    }
}
</style>