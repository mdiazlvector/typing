<template>
    <div class="custom-form">
        <form>
            <h2 v-if="mensaje !== ''">{{devuelveMensaje}}  </h2>
            <input
                id="lo-tecleado"
                v-model="fraseEscrita"
                v-bind:disabled="!iniciado"
                v-on:keyup="testValor"
            />
            <button
                v-on:click.prevent="empezar"
            >
            Empezar
            </button>  
            <!-- <div>
                {{fraseEscrita}}
            </div> -->

        </form>
    </div>
</template>

<script>
export default {
    name: 'CustomForm',
    props: {
        fraseInicial: String,
        terminadoHandler: Function,
    },
    data: function(){
        return {
            datos: {
                fraseEscrita: '',
            },
            iniciado: false,
            inicio: Date.now(),
            mensaje: '',
            tiempo: 0,
            haSidoEscrito: false,
            tiempoTranscurrido:0
        }
    },
    methods: {
        empezar: function () {
            this.iniciado = true;
            this.fraseEscrita = '';
            this.mensaje = '';
            this.tiempo = Date.now;
            this.tiempoTranscurrido = '';
        },
    testValor: function() {
        // this.tiempoTranscurrido = (Date.now() - this.tiempo) / 1000;
        // const resultado = this.fraseInicial.indexOf(this.datos.fraseEscrita);
        const ahora = Date.now();
        this.tiempoTranscurrido = (ahora - this.inicio) / 1000;

        const resultado = this.fraseInicial.indexOf(this.fraseEscrita);
      if (resultado !== 0) {
        // hay error
        this.mensaje = 'Vas mal. Llevas ';
      } else if (this.fraseInicial === this.fraseEscrita) {
        // terminado correctamente
        this.mensaje = 'Felicidades. Has tardado ';
        this.iniciado = false;
      } else {
        // vamos bien
        this.mensaje = 'Vas bien. Llevas ';
      }
    },
  },
  computed: {
    devuelveMensaje: function() {
      return this.mensaje + this.tiempoTranscurrido
    }
  }
}
</script>
<style>

</style>