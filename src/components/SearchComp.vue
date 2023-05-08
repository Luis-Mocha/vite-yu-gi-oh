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
        <select name="selectArchetype" id="selectArchetype" v-model="store.inputArchetype">
            <option v-for="(elem, index) in store.arrayArchetype" :key="index" :value="elem.archetype_name">
                {{ elem.archetype_name }}
            </option>
        </select>
        <button type="submit" @click.prevent="$emit('selezionaArchetipo')">
            Cerca Archetipo
        </button>
    </div>

    <!--
    <div>
        <input type="search" name="" id="" placeholder="Search Card by name" v-model="store.testoRicerca" @keyup.enter="$emit('nomeEmit')" @keyup.delete="$emit('nomeEmit')"> 
        <button type="submit" @click.prevent="$emit('nomeEmit')">
            Ricerca per nome
        </button>
    </div>
    -->
    <!-- @keyup.prevent="$emit('nomeEmit') -->

</template>

<style lang="scss" scoped>

</style>