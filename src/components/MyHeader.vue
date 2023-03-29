<script>
    export default {
        name: "MyHeader"
    }
</script>


<template>
    <header class="d-flex justify-content-start align-items-center">
        <div class="img-wrapper">
            <img src="http://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="YU-GI-HO logo">
        </div>
        <h1>Yu-Gi-Ho Api</h1>
    </header>
</template>


<style lang="scss" scoped>
    header{
        padding: 40px;
        line-height: 70px;
    }
    img{
        height: 50px;
    }
</style>