<script>
    import {store} from '../store'
    import SingoloPersonaggio from './SingoloPersonaggio.vue';

    export default {
        name: 'PersonaggiComp',
        components: {
            SingoloPersonaggio,
        },
        data() {
            return {
                store
            }
        },
        
    }
    
</script>


<template>

    <div class="container text-success text-center d-flex flex-wrap justify-content-between py-3">
        <SingoloPersonaggio 
        v-for="(elem, index) in store.arrayPersonaggi" :key="index"
        :infoPersonaggi="elem"
        />
    </div>    

</template>

<style lang="scss" scoped>

</style>