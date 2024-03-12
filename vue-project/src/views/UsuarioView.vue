<template>
  <div class="about">
    <h1>Welcome {{ nome }}</h1>
    <input type="text" :value="nome" @input="mudouTexto" />
    <p v-if="nome.length > 10">Nome loongo!</p>
    <p v-else>Nome curto!</p>
    <CustomTable :usuarios="usuarios" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import CustomTable from '@/components/CustomTable.vue';

const nome = ref("Teste");
const usuarios = ref([{ id: 1, nome: "Ana" }, { id: 2, nome: "Carolina" }]);

function mudouTexto(e: any) {
  nome.value = e.target.value;
}

</script>
