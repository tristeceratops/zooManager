<script setup>
import { ref, computed } from 'vue';
import TestTable from './TestTable.vue';

const itemList = ref([
    { id: 1, nom: "Élément 1", description: "Description de l'élément 1" },
    { id: 2, nom: "Élément 2", description: "ADescription de l'élément 2" },
    { id: 3, nom: "Élément 3", description: "CDescription de l'élément 3" },
    { id: 11, nom: "Élément 11", description: "BDescription de l'élément 11" }
    // Ajoutez d'autres éléments au besoin
]);

const sortedItemList = computed(() => {
    // Triez la liste par ordre alphabétique du nom
    return itemList.value.slice().sort((a, b) => a.description.localeCompare(b.description));
});



const actualList = ref(itemList);

const changeSorting= computed(() => {
    return  actualList === itemList ? sortedItemList : itemList;
});
    
</script>

<template>
    <div>
      <h1>Liste des éléments</h1>
      <TestTable></TestTable>
    </div>
</template>

<style scoped>
</style>
