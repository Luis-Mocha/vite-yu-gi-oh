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

    <header>
        <h1 :class="classiProps" class="p-0 m-0"> {{ titoloProps }} </h1>
    </header>

</template>

<style lang="scss" scoped>

</style>

