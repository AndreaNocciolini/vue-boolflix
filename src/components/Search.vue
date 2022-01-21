<template>
  <div class="header-container">
      <div class="search-bar-container">
          <input class="me-3" @keyup.enter="$emit('doSearch', inputText)" v-model="inputText" type="text" placeholder="Search..." name="search">
          <button class="btn-danger rounded-3" type="submit" @click="$emit('doSearch', inputText)"><i class="fas fa-search"></i></button>
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

<style lang="scss" scoped>
    .fas.fa-search{
        color: white;
    }
</style>