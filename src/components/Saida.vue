<template>
    <div>
        <div v-if="adivinhado!= ''">
            <div v-if="adivinhado == sorteado">
                Acertou!!
            </div>
            <div v-else-if="adivinhado < sorteado">
                tente maior
            </div>
            <div v-else-if="adivinhado > sorteado">
                tente menor
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        'adivinhado': Number,
         'sorteado': Number
    }
}
</script>

<style>

</style>
