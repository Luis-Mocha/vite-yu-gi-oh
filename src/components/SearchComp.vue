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

    <div class="searchDiv">
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

        
        <div>
            <input type="search" name="inputName" id="inputName" placeholder="Filter by name" v-model="store.testoRicerca" >
        </div>
    </div>

    

</template>

<style lang="scss" scoped>
    .searchDiv {
        display: flex;
        justify-content: space-evenly;
        padding-top: 15px;
        font-size: 18px;
    }
</style>