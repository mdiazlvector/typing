<template>
    <div>
        <h1>Juego de escribir</h1>
        <h2>{{fraseInicial}}</h2>  
    </div>
</template>

<script>
export default {
    name: 'CustomHeader',
    props: {
        fraseInicial: String,
    }
}
</script>
<style>

</style>