<script>
    import { ref, reactive } from "vue"

    export default {
        setup() {
            const title = ref("Ref y Reactive")
            const list = reactive({ 
                name: "Darth Vader", 
                side: "Dark"
            })

            //Desde el atributo "value" se puede modificar el valor
            //a la variable reactiva creada con ref
            // title.value = "Reasignar"

            list.name = "Skywalker"

            return {
                title,
                list
            }
        }
    }
</script>

<template>
    <h2>Clase 14</h2>
    <h3>{{ title }}</h3>
    <p>
        La forma de utilizar variables reactivas
        con Composition API es con "ref" y "reactive".
    </p>
    <p>
        Ref se utiliza solo cuando la variable reactiva es 
        un dato de tipo primitivo, a diferencia de reactive
        que es para objetos. Antes de explicar la razón de esto
        se tiene que saber que es gracias al objeto Proxy, que 
        VueJS puede saber que un valor ha 
        cambiado y así propagar ese cambio a todos los lugares 
        dónde se use ese valor, esto es a lo que conocemos 
        cómo reactividad. Sin embargo, el objeto Proxy tiene 
        ciertas reglas para funcionar, la principal es que 
        necesita envolver a un objeto, no puede funcionar 
        sobre variables que solo tengan valores de tipo 
        primitivo (números, cadenas de texto, booleanos, etc).
        Es por eso que cuándo se trata de valores de tipo primitivo, 
        cómo es el caso de la función ref, siempre tenemos que usar 
        el atributo value para acceder al valor y así mantener
        la reactividad, pues por detrás estará creando un objeto 
        con la propiedad value, a la cuál le asignará el valor que 
        ref recibe por argumento.
    </p>
    <p>
        Mientras tanto cuándo usamos reactive, el valor que pasamos por 
        argumento ya es un objeto, así que VueJS puede aplicarle todo 
        su sistema de reactividad sin necesidad de hacer nada más.
    </p>
    <p>
        Es por esto que en variables creadas con ref necesitamos usar 
        el atributo value, pero en variables creadas con reactive, no es 
        necesario. Esto también significa que debemos tener cuidado al 
        usar cosas cómo el spread operator (…), ya que estaríamos 
        extrayendo el valor del objeto Proxy, y por lo tanto obtenemos 
        el valor, más no la referencia, y podemos perder la reactividad.
    </p>
    <small>Se uso reactive para hacer reactivo este objeto</small>
    <p>{{ list }}</p>
</template>