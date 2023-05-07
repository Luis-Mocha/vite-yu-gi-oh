<script>

    export default {
        name: 'HeaderComp',
        props: [
            'titoloProps',
            'classiProps'
        ]
    }
    
</script>


<template>

    <h1 :class="classiProps"> {{ titoloProps }} </h1>

</template>

<style lang="scss" scoped>

</style>

