<script>
    export default {
        data() {
            return {
                isOpenModal: false
            }
        },
        methods: {
            toggleModal() {
                this.isOpenModal = !this.isOpenModal
            }
        }
    }
</script>

<template>
    <h2>Clase 7</h2>
    <button @click="toggleModal">Abrir modal</button>
    <teleport to="body">
        <div class="modal" v-show="isOpenModal">
            <div class="content-modal">
                <p>Hola soy un modal</p>
                <button @click="toggleModal">Cerrar modal</button>
            </div>
        </div>
    </teleport>
</template>

<style>
    .modal {
        display: flex;
        place-content: center;
        place-items: center;
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        background-color: rgba(0, 0, 0, 0.411);
    }

    .content-modal {
        display: flex;
        text-align: center;
        padding: 24px;
        box-sizing: border-box;
        border-radius: 14px;
        justify-content: center;
        flex-direction: column;
        width: 400px;
        height: 350px;
        background-color: #3d3d3d;
    }
</style>