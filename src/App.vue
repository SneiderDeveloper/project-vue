<script>
import HelloWorld from './components/HelloWorld.vue'
import Clase6 from './components/Clase6.vue'
import Clase7 from './components/Clase7.vue'
import Clase10 from './components/Clase10.vue'
import Clase11 from './components/Clase11.vue'
import Clase13 from './components/Clase13.vue'
import Clase14 from './components/Clase14.vue'
import Clase15 from './components/Clase15.vue'
import Clase16 from './components/Clase16.vue'
import Clase17 from './components/Clase17.vue'
import Clase18 from './components/Clase18.vue'
import Clase19 from './components/Clase19.vue'
import Clase20 from './components/Clase20.vue'
import { defineAsyncComponent } from 'vue'

const Input = defineAsyncComponent(() =>
  import("./components/Input.vue")
)

export default {
  components: {
    HelloWorld,
    Input,
    Clase6,
    Clase7,
    Clase10,
    Clase11,
    Clase13,
    Clase14,
    Clase15,
    Clase16,
    Clase17,
    Clase18,
    Clase19,
    Clase20,
  },
  data() {
    return {
      optionsNav: [
        "Clase6",
        "Clase7",
        "Clase10",
        "Clase11",
        "Clase13",
        "Clase14",
        "Clase15",
        "Clase16",
        "Clase17",
        "Clase18",
        "Clase19",
        "Clase20",
    ],
      isActive: "HelloWorld"
    }
  },
  methods: {
    changeComponent() {
      this.isActive = this.isActive === "HelloWorld" ? "Input" : "HelloWorld"
    }
  }
}
</script>

<template>
  <div class="wrapper">
    <nav class="nav">
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src="/vite.svg" class="logo" alt="Vite logo" />
        </a>
        <a href="https://vuejs.org/" target="_blank">
          <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
        </a>
      </div>
      <button @click="changeComponent">Home/Input</button>
      <li v-for="option in optionsNav" key="option" @click="isActive = option">{{ option }}</li>
    </nav>
    <div class="content">
      <component :is="isActive"></component>
    </div>
  </div>
</template>

<style scoped>

.wrapper {
  display: grid;
  grid-template-columns: 30% 1fr;
}

.content {
  text-align: center;
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.nav {
  display: flex;
  gap: 1.4rem;
  margin: 0;
  padding: 24px;
  flex-direction: column;
  max-height: 100dvh;
  overflow: auto;
  box-sizing: border-box;
}

.nav::-webkit-scrollbar {
  display: none;
}

.nav li {
  text-align: center;
  list-style: none;
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 0.6em 1.2em;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  background-color: #1a1a1a;
  cursor: pointer;
  transition: border-color 0.25s;
}
</style>
