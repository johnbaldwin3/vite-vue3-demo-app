<script setup lang="ts">
import { ref, defineProps, Teleport, defineEmits } from 'vue'

defineProps<{ notify: boolean }>()
const emit = defineEmits<{
  (e: 'notificationEmit', value: boolean): void
}>()

const someNotification = ref('This nested notification message teleports outside of the app to the `body`, skipping over and outside of parent component and DOM')

</script>

<template>
  <div class="child-component-title">I'm a child component, but I love my parent component, Hello World.</div>
  <Teleport to="body"> 
    <div class="modal" v-if="notify">
      <div>
        Notification: {{ someNotification }}
      </div>
      <div>
        <button class="modal-button" @click="$emit('notificationEmit', false)">Close</button>
      </div>
    </div>
  </Teleport>
</template>

<style scoped>
.child-component-title {
  padding-top: 20px;
}

.modal {
  position: fixed;
  z-index: 999;
  top: 20%;
  left: 50%;
  width: 300px;
  margin-left: -150px;
  background-color: #F56600; /* Clemson Orange */
  border: 1px solid darkgray;
  padding: 20px;
  font-size: 20px;
  color: white;
}

.modal-button {
  background-color: #522D80; /* Regalia Purple */
  color: white;
}
</style>