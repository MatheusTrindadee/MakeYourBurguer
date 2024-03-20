<template>
    <div>
        <p>{{ compEmail }}</p>
        <Picture/>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou procurando emprego.</p>
        <p>Utilizo as seguintes tecnologias:</p>
        <ul>
            <li v-for="(tecnologia, index) in tecnologias" :key="index">{{ tecnologia }}</li>
        </ul>
        <select>
            <option v-for="(opcao, index) in opcoes" :key="index">{{ opcao }}</option>
        </select>
        <ul>
            <li v-for="controle in controles" :key="controle.id">{{ controle.tipo }}</li>
        </ul>
        <div>
            <button @click="showEmail">{{ textoBotao }}</button>
        </div>
        <h4>Mande um email para: <p v-show="mostrar_email"> {{ email }} </p> </h4>
        <p>Para acessar meu portifólio, basta clicar no meu <a v-bind:href="meu_link" target="_blank">link</a></p>
    </div>
</template>

<script>
    import Picture from "./Picture.vue";

    export default {
        name: 'Info',
        components: {
            Picture,
            Reutilizacao
        },
        promps: {
            compEmail: String
        },
        data() {
            return {
                esta_trabalhando: false,
                mostrar_email: false,
                email: 'matheus@gmail.com',
                meu_link: 'https://www.youtube.com/watch?v=FtcreaLDeWA&list=PLnDvRpP8BnezDglaAvtWgQXzsOmXUuRHL&index=10',
                textoBotao: 'Mostrar Email',
                tecnologias: ['JavaScript', 'PHP', 'Python'],
                opcoes: ['sorvete', 'picole', 'palleta'],
                controles: [
                    {id: 1, tipo: 'Remoto'},
                    {id: 2, tipo: 'Ar-Condicionado'},
                    {id: 3, tipo: 'Analógico'}
                ]
            }
        },
        methods: {
            showEmail() {
                this.mostrar_email = !this.mostrar_email;
                if (this.mostrar_email) {
                    this.textoBotao = 'Esconder email'
                }else{
                    this.textoBotao = 'Mostrar email'
                }
            }
        }
    }
</script>

<style scoped>
    p {
        color: red;
    }
</style>