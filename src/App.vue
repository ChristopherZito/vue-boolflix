<template>
  <div>
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
