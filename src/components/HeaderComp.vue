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
        background-color: rgb(33,37,41);
        
        h1 {
            color: rgb(212,143,56);
            font-family:'Times New Roman', Times, serif;
            font-weight: 800;
            font-size: 50px;
        }
    }

</style>

