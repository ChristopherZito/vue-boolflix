<template>
  <div>
    <header>
      <Header
      @vuoto="text"
      @arrFilm="traArr"
      />
    </header>
    <main>
      <Mainbody
      :inText="outText"
      :inArr="outArr"
      
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
    }
  },
  methods: {
    text(dato){
      this.outText = dato;
    },
    traArr(dato){
      this.outArr = dato;
    }
  }
}

/* key : 51b734778d60901847898e72aa9d7466 */
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
main{
  background-color: gray;
  padding: 50px 0;
  /* debug */
  height: 700px;
}
</style>
