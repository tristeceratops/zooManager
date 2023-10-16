<script setup>
import { ref, computed } from 'vue';

const itemList = ref([
    { id: 1, nom: "Élément 1", description: "Description de l'élément 1" },
    { id: 2, nom: "Élément 2", description: "ADescription de l'élément 2" },
    { id: 3, nom: "Élément 3", description: "CDescription de l'élément 3" },
    { id: 11, nom: "Élément 11", description: "Description de l'élément 11" }
    // Ajoutez d'autres éléments au besoin
]);

const sortedItemList = computed(() => {
    // Triez la liste par ordre alphabétique du nom
    return itemList.value.slice().sort((a, b) => a.description.localeCompare(b.description));
});
</script>

<template>
    <div>
      <h1>Liste des éléments</h1>
      <button>Trier par nom</button>
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nom</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in sortedItemList" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.nom }}</td>
            <td>{{ item.description }}</td>
          </tr>
        </tbody>
      </table>
    </div>
</template>

<style scoped>
</style>
