<script>
    export default {
        data() {
            return {
                fruitFavorite: ""
            }
        }
    }
</script>

<template>
    <input placeholder="Fruta favorita" v-model="fruitFavorite"/>
</template>