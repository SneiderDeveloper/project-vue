<script>
    import { ref } from "vue"

    export default {
        setup(props, context) {
            const titleClass = ref("Contexto") 
            console.log("contexto", context)

            //Variable publica
            context.expose({
                titleClass
            })

            return {
                titleClass
            }
        }
    }
</script>

<template>
    <h2>Clase 18</h2>
    <h3>{{ titleClass }}</h3>
    <p>
        El contexto se puede acceder desde el segundo 
        parametros de la función setup. Desde el
        contexto se puede acceder al los atributos
        (cuando se envia props desde el componente
        padre, en el componente hijo se reciben los
        props desde el objeto props. Cuando esos props
        no se reciben entonces vue los toma como atributos
        y se veran en el atributo "attrs" del contexto)
        desde el "attrs", también tiene la función emit
        y la función expose que permite hacer publica 
        variables que pueden ser accedidas desde el 
        componente padre.
    </p>
    <p>Mirar la consola</p>
</template>