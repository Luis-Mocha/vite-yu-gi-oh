<script>
    import {store} from '../store'

    export default {
        name: 'SearchComp',

        data() {
            return {
                store
            }
        },
        
    }
    
</script>


<template>

    <div>
        <input type="text" placeholder="Search Card" v-model="store.testoRicerca" @keyup.enter="$emit('nomeEmit')" @keyup.delete="$emit('nomeEmit')"> <!-- @keyup.prevent="$emit('nomeEmit') -->
        <button type="submit" @click.prevent="$emit('nomeEmit')">
            Ricerca per nome
        </button>
    </div>

</template>

<style lang="scss" scoped>

</style>