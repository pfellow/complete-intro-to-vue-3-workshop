<script lang="ts">
import BaseCounter from './components/BaseCounter.vue'

export default {
  components: {
    BaseCounter
  },
  data: () => ({
    message: 'Hello it works',
    listOfNumbers: [
      {
        id: 1,
        uuid: 'ea188a02-4737-4282-ad92-c3cbd0320c9b',
        text: 'fine',
        arr: [1, 2, 3]
      },
      {
        id: 2,
        uuid: 'd94c2ee6-93d2-4b5e-aba5-6fc8ca0945c4',
        text: 'dash',
        arr: [1, 2, 3]
      },
      {
        id: 3,
        uuid: '65fecb01-82f9-4957-b9bb-4e571c030ef7',
        text: 'rough',
        arr: [1, 2, 3]
      },
      {
        id: 4,
        uuid: '512d4fe3-cc75-4b36-a251-7d6848b1c041',
        text: 'faint',
        arr: [1, 2, 3]
      },
      {
        id: 5,
        uuid: 'ebb9d844-f4ea-422c-82da-e6e85bc5600f',
        text: 'pull',
        arr: [1, 2, 3]
      }
    ]
  })
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="Counter" />
    </div>
  </header>

  <main>
    <BaseCounter />
    <hr />
    <p v-if="message.length % 2 === 0">Even: {{ message }}</p>
    <p v-else>Odd: {{ message }}</p>
    <ul>
      <li v-for="(item, index) in listOfNumbers" :key="`item-${index}`">
        {{ item.uuid }}
        <ul>
          <li v-for="(number, index) in item.arr" :key="`number-${index}`">
            {{ number }}
          </li>
        </ul>
      </li>
    </ul>
  </main>
</template>
