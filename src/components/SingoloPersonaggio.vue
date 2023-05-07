<script>

    export default {
        name: 'SingoloPersonaggio',
        props: ['infoPersonaggi']        
        
    }
    
</script>


<template>

    <div class="card-personaggio text-center text-light rounded col-12 col-sm-6 col-md-4 col-lg-3">
        <img :src="infoPersonaggi.card_images[0].image_url" alt="">

        <div class="card-info p-2">
            <h2 class="p-0">
                {{ infoPersonaggi.name }}
            </h2>        

            <p class="">
                {{ infoPersonaggi.desc }}
            </p>
        </div>
    </div>

</template>

<style lang="scss" scoped>
    .card-personaggio {
        background-color: rgb(33,37,41);
        margin-top: 10px;
        margin-bottom: 10px;

        width: calc(100% / 2 - 5px);

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

            p {
                padding: 0;
                max-height: 120px;
                overflow: auto;

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