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
}
</style>