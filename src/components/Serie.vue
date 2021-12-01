<template>
    <section>
        <div>
            <h3>
                Titolo oroginale: {{series.original_name}}
            </h3>
             <h3>
                Titolo: {{series.name}}
            </h3>
            <h2>
                Lingua: {{series.original_language}}
                <figure> 
                    <img v-if="film.original_language === `it`"
                    src="../assets/italia.png" alt="Lingua italiana">
                    <img v-else-if="film.original_language === `en`" 
                    src="../assets/america.png" alt="Lingua inglese">
                    <img v-else src="../assets/world.png" alt="Lingua non riconosciuta">
                </figure> 
            </h2>
            <h2>
                Voto: {{series.vote_average}}
            </h2>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Element',
    props:{
        series: Object,
    },
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
    /* debug */
    height: 400px;

    h3,h2 {
        margin: 10px 0;
    }

    figure {
        display: inline-block;
        img {
            width: 30px;
        }
    }
}
</style>