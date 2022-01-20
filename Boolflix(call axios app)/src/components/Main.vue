<template>
  <main class="row row-cols-4">
    <Card v-for="(card, index) in cards" :key="index" :movie="card"/>
  </main>
</template>

<script>
import Card from './Card.vue'

export default {
  name: 'Main',
  components: {
    Card,
  },
  props: {
    cards: {
      type: Array,
      default() {
        return []
      }
    }
  }
}
</script>

<style>

</style>