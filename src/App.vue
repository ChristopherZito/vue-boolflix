<template>
  <div>
    <header>
      <Header
      @vuoto="text"
      @filerie="inRicerca"
      />
    </header>
    <main>
      <Mainbody
      :inText="outText"
      :inFilm="films"
      :inSerie="series"
      />
    </main>
  </div>
</template>

<script>
import axios from "axios"
import Header from './components/Header.vue'
import Mainbody from './components/Mainbody.vue'


export default {
  name: 'App',
  components: {
    Header,
    Mainbody
  },
  data(){
    return {
      outText:"",
      films: [],
      series: [],
    }
  },
  methods: {
    text(dato){
      this.outText = dato;
    },
    inRicerca(dato){
      if(dato !== ""){
        axios
          .get("https://api.themoviedb.org/3/search/movie?api_key=51b734778d60901847898e72aa9d7466&language=en-US&query="+ dato + "&page=1&include_adult=false")
          .then((movie) => {
            this.films = movie.data.results
            /* console.log(this.films); */
        });
        axios
        .get("https://api.themoviedb.org/3/search/tv?api_key=51b734778d60901847898e72aa9d7466&language=en-US&page=1&query="+ dato +"&include_adult=false")
        .then((serie) => {
          this.series = serie.data.results
          /* console.log(serie.data.results); */
        })
      }
    }

  }
}

</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
main{
  background-color: #4f4f4f;
  padding: 50px 0;
  min-height: 925px;
  /* debug */
  /* height: 700px; */
}
@import '~@fortawesome/fontawesome-free/css/all.min.css';
</style>
