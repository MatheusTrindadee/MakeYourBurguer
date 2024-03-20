<template>
    <div>
        <img :src="avatar" :alt="descricao">
        <Reutilizacao/>
    </div>
</template>

<script>
    import Reutilizacao from "./Reutilizacao.vue";

    export default {
        name: 'Picture',
        components: {
            Reutilizacao
        },
        data() {
            return {
                avatar: '/img/asda.png',
                descricao: 'Gato Duvidoso'
            }
        }
    }
</script>

<style>
    img{
        height: 100px;
        width: 100px;
    }
</style>