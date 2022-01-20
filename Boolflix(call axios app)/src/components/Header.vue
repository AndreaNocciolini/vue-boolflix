<template>
  <header>
      <div class="search">
          <input type="text" v-model="textSearch" @keyup.enter="$emit('doSearch', textSearch)" placeholder="Write here...">
          <button @click="$emit('doSearch', textSearch)">Search</button>
      </div>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return {
            textSearch: '',
        }
    }
}
</script>

<style>

</style>