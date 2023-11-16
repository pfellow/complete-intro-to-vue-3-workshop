<script lang="ts">
export default {
  props: {
    favorList: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <ul>
    My favorites:
    <li v-for="(actor, index) in favorList" :key="index">
      {{ actor }}
    </li>
  </ul>
</template>
