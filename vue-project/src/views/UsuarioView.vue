<template>
  <div>
    <h1>Welcome {{ nome }}</h1>
    <input type="text" :value="nome" @input="mudouTexto"/>
    <p v-if="nome.length > 10">Nome longo</p>
    <p v-else>Nome curto</p>
    <table>
      <thead>
        <td>Id</td>
        <td>Nome</td>
      </thead>
      <tbody>
        <tr v-for="usuario in usuarios">
          <td>{{ usuario.id }}</td>
          <td>{{ usuario.nome }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const nome = ref("teste");

const usuarios = ref([ {id:1, nome: "Geraldo"}, {id:2, nome:"Milena"}]);

function mudouTexto(e: any) {
  nome.value = e.target.value;
}

// defineProps<{
//   usuarios: {id: number, nome: string} []
// }>()
</script>
