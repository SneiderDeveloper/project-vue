<script>
    import { computed, ref } from "vue"

    export default {
        setup() {
            const name = ref("Mateo")
            const lastName = ref("Narvaez")

            const fullName = computed(() => {
                return `${name.value} ${lastName.value}`
            })

            return {
                name, 
                lastName,
                fullName
            }
        }
    }
</script>

<template>
    <h2>Clase 16</h2>
    <h3>Variables computadas</h3>
    <p>{{ name }}</p>
    <p>{{ lastName }}</p>
    <small>Esta es una variable computada</small>
    <p>{{ fullName }}</p>
</template>