<script>
    export default {
        data() {
            return {
                text: "Clase 10"
            }
        },
        beforeCreate() {
            console.log("beforeCreate", this.$data, this.$el)
        },
        created() {
            console.log("created", this.$data, this.$el)
        },
        mounted() {
            console.log("mounted", this.$data, this.$el)
        }
    }
</script>

<template>
    <h2>{{ text }}</h2>
    <p>
        Esta clase se trata sobre el ciclo de vida de los componentes
        en Vue. Durante el ciclo de vida de un componente se disparan
        diferentes eventos desde que se crean hasta que se destruyen.
        En Vue es posible ejecutar código cada vez que suceda algún
        evento. Se esta ejecuando un console.log por los eventos:
        beforeCreate, created y mounted (Mirar la consola).
    </p>
    <p>Hooks del ciclo de vida:</p>
    <ol>
        <li>beforeCreate</li>
        <li>created</li>
        <li>beforeMount</li>
        <li>mounted</li>
        <li>beforeUpdate</li>
        <li>updated</li>
        <li>beforeUnmount</li>
        <li>unmounted</li>
    </ol>
</template>