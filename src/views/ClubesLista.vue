<template>
  <v-container>
    <h2 class="text-h5 text-center mb-3 mt-5">Classificação dos clubes</h2>
    <ClubesTabela :clubes="clubesLista"/>
  </v-container>
</template>
<script>
import ClubesTabela from '../components/ClubesTabela';
export default {
  name: 'ClubesLista',
  components: {
    ClubesTabela
    },
  data() {
    return {
      clubesLista: []
    }
  },
  created() {
    fetch('https://hackthon-decola.firebaseio.com/clubes-lista.json')
      .then(response => response.json())
      .then(json => {
        this.clubesLista = json;
      })
  },
  
}
</script>