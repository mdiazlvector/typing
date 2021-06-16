<template>
    <div>
        <h1>Juego de escribir</h1>
        <cite>{{frase}}</cite>  
    </div>
</template>

<script>
export default {
    name: 'CustomHeader',
    props: {
        frase: String,
    }
}
</script>
<style>

</style>