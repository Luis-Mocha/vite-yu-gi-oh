<script>
    import { store } from '../store';

    export default {
        name: 'SingoloPersonaggio',
        props: ['infoPersonaggi'] ,
        
        data() {
            return {
                store
            }
        },
        
    }
    
</script>


<template>

    <div class="card-personaggio text-center text-light rounded col-12 col-sm-6 col-md-4 col-lg-3" :class=" (infoPersonaggi.name.toLowerCase().includes(store.testoRicerca.toLowerCase()) ) ? 'd-block' : 'd-none' ">
        <img :src="infoPersonaggi.card_images[0].image_url" :alt="'Immagine ' + infoPersonaggi.name">

        <div class="card-info p-2">
            <h2 class="p-0 mt-2">
                {{ infoPersonaggi.name }}
            </h2>        

            <span>Description:</span>
            <p>
                {{ infoPersonaggi.desc }}
            </p>

            <span>Archetipo: {{ infoPersonaggi.archetype }}</span>
        </div>
    </div>

</template>

<style lang="scss" scoped>
    .card-personaggio {
        background-color: rgb(33,37,41);
        border-width: 4px;
        border-color: white;
        border-style:double;
        margin-top: 10px;
        margin-bottom: 10px;

        width: calc(100%);

        @media screen and (min-width: 425px) {
            width: calc(100% / 2 - 10px);
        };

        @media screen and (min-width: 576px) {
            width: calc(100% / 3 - 5px);
        };
        
        @media screen and (min-width: 992px) {
            width: calc(100% / 4 - 15px);
        };

        img {
            width: 100%;
            margin: auto;
        }

        .card-info {
            h2 {
                text-transform: uppercase;
                font-size: 16px;
                height: 60px;

                @media screen and (min-width: 576px) {
                    font-size: 19px;
                };
            }

            span {
                color: rgb(212,143,56);
            }

            p {
                padding: 0;
                height: 120px;
                overflow: auto;
                border-width: 0px 0px 1px 1px;
                border-style: solid;
                border-color: rgb(212,143,56);


                /* width */
                &::-webkit-scrollbar {
                width: 4px;
                }

                /* Track */
                &::-webkit-scrollbar-track {
                background: #555; 
                }
                
                /* Handle */
                &::-webkit-scrollbar-thumb {
                background: rgb(212,143,56); 
                }
            }
        }
    }
</style>