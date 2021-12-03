<template>
    <div id="container">
        <div>
            <h1>
                Boolflix
            </h1>
        </div>
        <div>
            <input
            @keyup.enter="searching" 
            type="text"
            v-model="toSearch" 
            placeholder="Cerca un Film" >
            <button @click="searching">
                Cerca
            </button>
        </div>
    </div>
</template>

<script>

export default {
    name: 'Header',
    data() {
        return {
            toSearch: "",
            load:"",
        }
    },
    methods: {
        searching() {
            /* console.log("inizio a cercare"); */
            this.load = "Inserisci un nome nella ricerca"
            this.$emit(`vuoto`,this.load)
            this.$emit(`filerie`,this.toSearch)
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