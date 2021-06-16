<template>
    <div class="custom-form">
        <form>
            <div>
                {{fraseEscrita}}
            </div>
            <input
                v-model="fraseEscrita"
                v-bind:disabled="!iniciado"
            />
            <button
                v-on:click.prevent="empezar"
            >
                Empezar
            </button>  

        </form>
    </div>
</template>

<script>
export default {
    name: 'CustomForm',
    props: {
        fraseInicial: String,
    },
    data: function(){
        return {
            datos: {
            fraseEscrita: 'Bu',
            },
            iniciado: false,
        }
    },
    methods: {
        empezar: function(){
            this.iniciado = true;
        },
    },
}
</script>
<style>

</style>