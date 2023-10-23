<script setup>
    import json from '../data/animal.json'
    import DemoGrid from './Grid.vue'

    import { ref } from 'vue'

    const searchQuery = ref('')
    const gridColumns = ['name', 'species','description','image']

</script>

<template>
  <form id="search">
    Search <input name="query" v-model="searchQuery">
  </form>
    <DemoGrid
        :data="json"
        :columns="gridColumns"
        :filter-key="searchQuery">
    </DemoGrid>
</template>


<style scoped>

</style>