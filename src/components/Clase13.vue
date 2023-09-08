<script>
    import { onBeforeMount, onMounted } from "vue"

    export default {
        setup() {
            onMounted(() => {
                console.log("Mount!!")
            })
        }
    }
</script>

<template>
    <h2>Clase 13</h2>
    <p>
        Los hooks del ciclo de vida se tienen que 
        acceder de forma diferente con Componsition API.
        Para empezar se tienen que importar directamente de
        vue. Además todos empiezan con on, por ejemplo,
        onMount, onBeforeMount. Al importar, estos hooks son
        una función que reciben un callback, dentro de este 
        callback podemos ejecutar cualquier cosa que queramos
        que pase cuando durante el ciclo de vida del componente
        se accione este evento.
    </p>
    <p>
        Con setup, los eventos beforeCreate y created ya no están
        disponibles, por que setup los reemplaza, el resto de eventos
        del ciclo de vida están disponibles.
    </p>
    <p>Mirar la consola</p>
</template>