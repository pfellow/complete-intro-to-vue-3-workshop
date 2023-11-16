<script lang="ts">
export default {
  data: () => ({
    counter: 10,
    incrementAmount: 1,
    counterTitle: 'Counter Standard'
  }),
  methods: {
    incrementCount() {
      this.counter += +this.incrementAmount
    }
  },
  watch: {
    counter(newValue) {
      if (newValue > 20) {
        this.counterTitle += ' Very Long'
      }
    }
  },
  computed: {
    displayTitle() {
      return 'Counter Standard' + (this.counter > 20 ? ' Very Long' : '')
    }
  }
}
</script>

<template>
  <h3>{{ displayTitle }}</h3>
  <p>{{ counter }}</p>
  <div>
    <label for="incrementAmount">Increment by: </label>
    <input type="number" v-model="incrementAmount" />
  </div>
  <button v-on:click="incrementCount">Increment count</button>
</template>
