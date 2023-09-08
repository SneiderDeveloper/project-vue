<script>
    export default {
        data() {
            return {
                show: true
            }
        }
    }
</script>

<template>
    <h2>Clase 6</h2>
    <button @click="show = !show">
        Show
    </button>
    <transition name="fade">
        <section v-show="show">
            <p>
                Vuee es muy poderoso. Tiene funciones muy poderosas.
            </p>
        </section>
    </transition>
</template>

<style>
/* -enter -> Cuando el elemento entra */
/* -leave -> Cuando el elemento sale */
/* -from -> Cuando inicia la transición */
/* -active -> Cuando la transición esta activa */
/* -to -> Cuando termina la transición */

.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.5s ease;
}

.fade-leave-to,
.fade-enter-from {
    opacity: 0;
}
</style>