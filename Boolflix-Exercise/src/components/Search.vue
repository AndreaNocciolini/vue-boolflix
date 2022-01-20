<template>
  <div class="header-container">
      <div class="search-bar-container">
          <input @keyup.enter="$emit('doSearch', inputText)" v-model="inputText" type="text" placeholder="Search..." name="search">
          <button type="submit" @click="$emit('doSearch', inputText)">Go!</button>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Search',
    data() {
        return {
            inputText:'',
        }
    },
}
</script>

<style>

</style>