<template>
    <div>
        <h2>Meu Formulário:</h2>
        <form action="" @submit="enviarFormulario($event)">
        <input type="text" v-model="nome"> <br>
        <input type="text" v-model="email"> <br>
        <Submit/>
    </form>
    </div>
</template>

<script>
    import inputText from "./form/inputText.vue";
    import Submit from "./form/Submit.vue";

    export default {
        name: 'Form',
        components: {
            inputText,
            Submit
        },
        data(){
            return{
                nome: '',
                email: ''
            }
        },
        methods: {
            enviarFormulario(e) {

                e.preventDefault();

                var nome = this.nome; 
                var email = this.email;

                console.log("Formulario");
                console.log("O nome enviado é: " + nome);
                console.log("O email enviado é: " + email);

                //Inserir dados no banco

            }
        }
    }
</script>