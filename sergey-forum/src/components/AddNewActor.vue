<script lang="ts">
export default {
  data: () => ({
    newActor: ''
  }),
  emits: ['add-actor']
}
</script>

<template>
  <label for="newActor">Add New </label>
  <input v-model="newActor" type="text" />
  <button @click="$emit('add-actor', this.newActor)">Add</button>
</template>
