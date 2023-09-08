<script>
    import { toRef, toRefs } from "vue"

    export default {
        props: {
            text: String
        },
        setup(props) {
            const { text } = toRefs(props)
            //Aplicar reactividad a solo un prop
            // const text = toRef(props, "text")

            return {
                text,
            }
        }
    }
</script>

<template>
    <button>{{ text }}</button>
</template>