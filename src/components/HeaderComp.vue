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
    header {
        height: 70px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

</style>

