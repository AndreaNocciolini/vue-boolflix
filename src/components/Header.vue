<template>
  <header class="d-flex justify-content-between align-items-center p-3">
      <h1>BOOLFLIX</h1>
      <Search @doSearch="$emit('calldoSearch', ($event))"
/>
  </header>
</template>

<script>
import Search from './Search.vue'

export default {
    name: 'Header',
    components: {
        Search,
    }
}
</script>

<style lang="scss" scoped>
  header {
    background-color: black;
    h1 {
      color: red;
    }
  }
</style>