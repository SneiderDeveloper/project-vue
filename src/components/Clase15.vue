<script>
    import { ref, reactive, watch } from "vue"

    export default {
        setup() {
            const title = ref("Watch")
            const characterName = ref("")
            const pastValue = ref("")
            const list = reactive({ 
                name: "Darth Vader", 
                side: "Dark"
            })

            watch(characterName, (value, oldValue) => {
                pastValue.value = oldValue
            })

            //Los objetos se tienen que envolver en una función
            //para que watch pueda escuchar los cambios correctamente.
            //Si paso solanmente el objeto list, entonces escucha
            //solamente la referencia del objeto.
            watch(() => list.name, (value, oldValue) => {
                console.log(value, oldValue)
            })

            return {
                title,
                characterName,
                pastValue
            }
        }
    }
</script>

<template>
    <h2>Clase 15</h2>
    <h3>{{ title }}</h3>
    <p>RealTime: {{ characterName }}</p>
    <p>Valor anterior: {{ pastValue }}</p>
    <input 
        placeholder="Nombre personaje favorito"
        v-model="characterName"
    />
</template>