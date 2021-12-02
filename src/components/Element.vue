<template>
    <section>
        <div 
        @mouseenter="info" 
        :class="dysplay == true? `none` : `display`"
        class="immagini" >
            <img  v-if="film.poster_path !== null"
            :src="`https://image.tmdb.org/t/p/w342` + film.poster_path" :alt="film.original_title">
            <img v-else src="https://image.tmdb.org/t/p/w342/wwemzKWzjKYJFfCeiB57q3r4Bcm.png" :alt="series.original_name">

        </div>
        <div 
        @mouseleave="image"
        :class="dysplay == false? `none` : `display`"
        class="info">
            <h3>
                Titolo oroginale: {{film.original_title}}
            </h3>
             <h3>
                Titolo: {{film.title}}
            </h3 >
            <h2>
                Lingua: {{film.original_language}}
                <figure>
                    <img v-if="film.original_language === `it`"
                    src="../assets/italia.png" alt="Lingua italiana">
                    <img v-else-if="film.original_language === `en`" 
                    src="../assets/america.png" alt="Lingua inglese">
                    <img v-else src="../assets/world.png" alt="Lingua non riconosciuta">
                </figure>
            </h2>
            <h2>
                Voto: {{film.vote_average}}
            </h2>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Element',
    props:{
        film: Object,
    },
    data() {
        return {
            dysplay:false,
        }
    },
    methods: {
        info(){
            this.dysplay = true;
        },
        image(){
            this.dysplay = false;
        }
    }
}
</script>

<style scoped lang="scss">
section {
    margin: 10px;
    padding: 10px;
    background-color: #000;
    border: 1px solid #fff;
    width: 350px;
    color: #fff;
    text-align: start;
    height:515px;

    h3,h2 {
        margin: 10px 0;
    }

    figure {
        display: inline-block;
        img {
            width: 30px;
        }
    }

    .immagini {
        height:515px;
        img {
            width: 100%;
        }
    }

    .info {
        width: 350px;
        height:515px;
    }
    .none {
        display: none;
    }

    .display {
        display: block;
    }
    
    
}

</style>.