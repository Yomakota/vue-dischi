<template>
        <div class="loader-container">
            <div class="loader position-absolute top-50 start-50 translate-middle">
                <div class="hourglass pb-3"></div>
                <div class="text-loader text-uppercase">Loading...</div>
            </div>
        </div>
</template>
<script>
export default {
    name: 'LoadingPage',
    data(){
        return{
        }
    }
}
</script>
<style lang="scss" scoped>
@import'../assets/scss/loader.scss';

.loader{
    color: white;
}
</style>