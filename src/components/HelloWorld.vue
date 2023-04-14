<script setup lang="ts">
import { ref } from 'vue'
import HelloSmallerWorld from './HelloSmallerWorld.vue';


defineProps<{ msg: string }>()
const colorsArray = ref([
  'orange', 'purple', 'black'
])
const count = ref(0)
const selectedStyleColor = ref('black')

const handleColorButtonClick = (color: string): void => {
  selectedStyleColor.value = color
}

const notificationDisplay = ref(false)
const handleEmit = (e: boolean) => {
  notificationDisplay.value = e
}
</script>

<template>
  <h1 class="the-message">{{ msg }}</h1>

  <p>
   Do some stuff:
  </p>
  <div class="buttons-div">
    <div v-for="(color, i) in colorsArray">
      <button
        class="style-change-button"
        :style="{ backgroundColor: color, color: 'white'}"
        @click="handleColorButtonClick(color)"
        :key="i"
      >
        {{ color }}
      </button>
    </div>
  </div>
  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Docs
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Docs</a>
  </p>
  <button type="button" @click="count++">letter-spacing is: {{ count }} | add letter-spacing</button>
  <button type="button" @click="count--"> subtract letter-spacing</button>
  <button type="button" @click="notificationDisplay = !notificationDisplay"> Show Notification</button>
  <HelloSmallerWorld
    @notificationEmit="handleEmit"
    :notify="notificationDisplay"
  ></HelloSmallerWorld>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}

.the-message {
  color: v-bind(selectedStyleColor);
  letter-spacing: v-bind('count + "px"');
}
.buttons-div {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.style-change-button {
  height: 30px;
  width: 60px;
  margin-right: 5px;
  margin-left: 5px;
  cursor: pointer;
}
</style>
