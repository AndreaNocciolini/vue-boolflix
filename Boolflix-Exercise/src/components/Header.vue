<template>
  <div>
      <h1>BOOLFLIX</h1>
      <Search @doSearch="$emit('calldoSearch', ($event))"
/>
  </div>
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