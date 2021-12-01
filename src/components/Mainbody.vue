<template>
    <div id="container">
        <div v-if="inArr.length == 0">
            <span v-if="inText == ``">
                {{wait}}
            </span>
            <span v-else>
                {{inText}}
            </span>
            
        </div>
        <div id="blocco" v-else>
            <Element 
            v-for="movie,i in inArr" :key="i"
            :film="movie"/>
        </div>
    </div>
</template>

<script>
/* import axios from "axios" */
import Element from '../components/Element.vue'

export default {
    name: 'Mainbody',
    components:{
        Element,
    },
    props: {
        inText: String,
        inArr: Array
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
    background-color:pink;
    /* debug */
    height: 500px;
    #blocco {
        display: flex;
        flex-wrap: wrap;
    }
    
}
</style>