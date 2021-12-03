<template>
    <div id="container">
        <div v-if="inFilm.length == 0">
            <span v-if="inText == ``">
                {{wait}}
            </span>
            <span v-else>
                {{inText}}
            </span>
            
        </div>
        <section v-else>
            <div class="blocco" >
                <Element 
                v-for="movie,i in inFilm" :key="i"
                :film="movie"/>
            </div>
            <div class="blocco">
                <Serie 
                v-for="serie,m in inSerie" :key="m"
                :series="serie"/>
            </div>
        </section>
    </div>
</template>

<script>
/* import axios from "axios" */
import Element from '../components/Element.vue'
import Serie from '../components/Serie.vue'

export default {
    name: 'Mainbody',
    components:{
        Element,
        Serie,
    },
    props: {
        inText: String,
        inFilm: Array,
        inSerie: Array,
    },
    data(){
        return {
            wait: "Cerca un film"
        }
    },
}
</script>

<style scoped lang="scss">
#container{
    width: 80%;
    margin: 0 auto;
    /* debug */
    /* background-color:pink; */
    /* height: 500px; */
    text-align: center;
    span {
        color: #fff;
        font-size: 40px;
    }

    .blocco {
        display: flex;
        flex-wrap: wrap;
    }
    
}
</style>