<template>
  <div>
    <font-awesome-icon icon="star" /> 
    <header>
      <Header
      @vuoto="text"
      @arrFilm="traArr"
      @arrSerie="traSerie"
      />
    </header>
    <main>
      <Mainbody
      :inText="outText"
      :inArr="outArr"
      :inSerie="outSerie"
      />
    </main>
  </div>
</template>

<script>
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
      outArr:[],
      outSerie:[],
    }
  },
  methods: {
    text(dato){
      this.outText = dato;
    },
    traArr(dato){
      this.outArr = dato;
    },
    traSerie(dato){
      this.outSerie = dato;
    }
  }
}

</script>

<style lang="scss">
/* 
<i class="far fa-star"></i> stella vuota
<i class="fas fa-star"></i> stella piena 
*/

/* @import '~@fontawesome/fontawesome-free/css/all.min.css'; */

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
</style>
