<script>

    export default {
        name: 'SingoloPersonaggio',
        props: ['infoPersonaggi']        
        
    }
    
</script>


<template>

    <div class="card-personaggio text-success text-center">
        <h2>
            {{ infoPersonaggi.name }}
        </h2>

        <img :src="infoPersonaggi.card_images[0].image_url_small" alt="">

        <p>
            {{ infoPersonaggi.type }}
        </p>
    </div>

</template>

<style lang="scss" scoped>

</style>