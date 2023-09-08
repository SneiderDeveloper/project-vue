<script>
    import { inject } from "vue"

    export default {
        setup() {
            const textCard = inject("textCard")

            return {
                textCard
            }
        }
    }
</script>

<template>
    <p>{{ textCard }}</p>
</template>