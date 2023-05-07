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

    <div class="text-success text-center">
        <SingoloPersonaggio 
        v-for="(elem, index) in store.arrayPersonaggi" :key="index"
        :infoPersonaggi="elem"
        />
    </div>

</template>

<style lang="scss" scoped>

</style>