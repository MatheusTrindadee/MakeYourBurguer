<template>
    <div>
        <h1>Olá Vue!</h1>
        <p>Meu nome é: {{ nome }}, eu tenho {{ age }} anos e tenho um {{ animal }}</p>
        <MultiplosEventos/>
        <Reutilizacao/>
    </div>
</template>

<script>
    import Reutilizacao from "./Reutilizacao.vue";
    import MultiplosEventos from './MultiplosEventos.vue'

    export default {
        name: 'PrimeiroComponente',
        components: {
            MultiplosEventos,
            Reutilizacao
        },
        data () {
            return {
                nome: "Matheus",
                age: "19",
                animal: "Cachorro"
            }
        }
    }
</script>