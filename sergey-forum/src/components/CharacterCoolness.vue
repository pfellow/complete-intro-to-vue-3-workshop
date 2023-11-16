<script lang="ts">
export default {
  props: {
    movie: {
      type: Object,
      required: true
    }
  },
  computed: {
    characterCoolness() {
      return this.movie.starring.length > 8 ? 'Such a good cast' : 'Not enough to evaluate!'
    }
  }
}
</script>

<template>
    <p>{{ characterCoolness }}</p>
</template>
