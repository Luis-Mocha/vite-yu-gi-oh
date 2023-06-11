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

    <div class="searchDiv bg-light">
        <div class="mb-3">
            <div class="d-flex flex-column">
                <label for="selectArchetype" class="form-label">Seleziona Archetipo</label>
                <select name="selectArchetype" id="selectArchetype" v-model="store.inputArchetype" @change="$emit('selezionaArchetipo')">
                    <option v-for="(elem, index) in store.arrayArchetype" :key="index" :value="elem.archetype_name">
                        {{ elem.archetype_name }}
                    </option>
                </select>
            </div>
            
        </div>

        
        <div class="mb-3 d-flex align-items-center">
            <input type="search" name="inputName" id="inputName" placeholder="Filter by name" v-model="store.testoRicerca" >
        </div>
    </div>

    

</template>

<style lang="scss" scoped>
    .searchDiv {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        padding-top: 15px;
        font-size: 18px;

        border-width: 8px;
        border-color: black;
        border-style: ridge;
    }
</style>