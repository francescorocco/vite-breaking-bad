<script>
   export default {
        name: 'CardOfCard',
        props: {
            image: String,
            name: String,
            archetype: String,
        }
    }
</script>


<template>
    <div class="card-container">
        <div class="ms-card">
            <img :src="image" alt="name">
        </div>
        <h4 class="text-center">{{ name }}</h4>
        <h5 class="text-center">{{ archetype }}</h5>
    </div>
</template>


<style scoped lang="scss">
    .card-container {
        padding: 5px;
    }
    .ms-card{
        padding: 30px;
    }
    img{
        width: 100%
    }

    h4{
        color: white;
        font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    }
</style>