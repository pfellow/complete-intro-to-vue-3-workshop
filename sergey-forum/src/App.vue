<script lang="ts">
import BaseMovie from "./components/BaseMovie.vue"
export default {
  components: {
    BaseMovie
  }
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  </header>

  <main>
    <BaseMovie />
  </main>
</template>
