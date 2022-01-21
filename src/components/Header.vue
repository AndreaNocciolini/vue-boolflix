<template>
  <header>
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

<style>

</style>