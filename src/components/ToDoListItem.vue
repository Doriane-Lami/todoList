<script setup>
import { defineEmits, defineProps } from "vue";
defineProps(["chose", "indexc"]);
defineEmits(["deletec", "fairec"]);
</script>

<template>
  <li>
    {{ chose.pourAfficher() }}
    <button @click="$emit('deletec', indexc)">Delete</button>
    <button @click="$emit('fairec', indexc)">Faire</button>
  </li>
</template>
