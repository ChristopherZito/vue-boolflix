<template>
    <div id="container">
        <div>
            <h1>
                Boolflix
            </h1>
        </div>
        <div>
            <input type="text" v-model="toSearch" placeholder="Cerca un Film" >
            <button @click="searching">
                Cerca
            </button>
        </div>
    </div>
</template>

<script>
import axios from "axios"
export default {
    name: 'Header',
    data() {
        return {
            toSearch: "",
            load:"",
            films: [],
            series: [],

        }
    },
    methods: {
        searching() {
            this.load = "Cercando"
            this.$emit(`vuoto`,this.load)
            this.inSearch = this.toSearch;
            console.log("inizio a cercare");
            axios
            .get("https://api.themoviedb.org/3/search/movie?api_key=51b734778d60901847898e72aa9d7466&language=en-US&query="+ this.inSearch + "&page=1&include_adult=false")
            .then((movie) => {
                this.films = movie.data.results
                /* console.log(this.films); */
                this.$emit(`arrFilm`,this.films)
            });
            axios
            .get("https://api.themoviedb.org/3/search/tv?api_key=51b734778d60901847898e72aa9d7466&language=en-US&page=1&query="+ this.inSearch +"&include_adult=false")
            .then((serie) => {
                this.series = serie.data.results
                /* console.log(serie.data.results); */
                this.$emit(`arrSerie`,this.series)
            })
            this.toSearch = "";
        }
    }
}
</script>

<style scoped lang="scss">
#container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #000;
    color: red;
    padding: 20px;

    button {
        padding: 10px;
    }

    input{
        padding: 10px;
    }
}
</style>