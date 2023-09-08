<script>
    import { onMounted, ref, watch } from 'vue';

    export default { 
        setup() {
            const inputRef = ref(null)

            onMounted(() => {
                inputRef.value.focus()
            })

            watch(inputRef, (value) => {
                console.log(value)
            })

            return {
                inputRef
            }
        }
    }
</script>

<template>
    <h2>Clase 20</h2>
    <p>Template refs</p>
    <p>
        Para tener las referencia de un
        elemento en Vue se utiliza el
        atributo ref.
    </p>
    <input ref="inputRef"/>
</template>