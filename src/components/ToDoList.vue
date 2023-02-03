<script setup>
import { reactive } from "vue";
import Chose from "../Chose.js";
import ToDoListItem from "./ToDoListItem.vue";
import ToDoForm from "./ToDoForm.vue";

const listeC = reactive([new Chose("menage"), new Chose("Vaiselle")]);

function handlerFaire(index) {
  listeC[index].faire();
}
function handlerDelete(index) {
  listeC.splice(index, 1);
}
</script>

<template>
  <h3>Liste des choses à faire</h3>
  <ul>
    <!--
    <li v-for="(truc,index) in listeC" :key=[truc._id]>
      {{ chose.pourAfficher() }}
      <button @click="handlerDelete(index)">Delete</button>
      <button @click="handlerFaire(index)">Faire</button>
    </li>
    -->
    <ToDoForm />
    <ToDoListItem
      v-for="(truc, index) in listeC"
      :key="truc.id"
      :chose="truc"
      :indexc="index"
      @deletec="handlerDelete(index)"
      @fairec="handlerFaire(index)"
    />
  </ul>
</template>