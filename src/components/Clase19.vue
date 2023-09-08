<script>
    import { provide, ref } from "vue"
    import Card from "./Card.vue"

    export default {
        components: {
            Card
        },
        setup() {
            const varInject = ref("Variable inyectada desde el padre")
            provide("textCard", varInject)
        }
    }
</script>

<template>
    <h2>Clase 19</h2>
    <h3>Provide/Inject</h3>
    <Card />
</template>