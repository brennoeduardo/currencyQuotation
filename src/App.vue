<template>
    <div class="container-grid-lg my-2 py-2 text-dark">
        <div class="card">
          <div class="card-header">
            <div class="h4"> Exibindo as Moedas</div>
          </div>

          <div class="card-body">

            <Centavos :moedas="moedas"/>

          </div>
        </div>
    </div>
</template>

<script>
import Centavos from './components/Centavos.vue'
import api from './server/api.js'
import { onMounted, reactive, toRefs } from 'vue';

export default {
  name: 'App',
  components: {
    Centavos
  },

  //Expor os dados da API do nosso component
  setup() {
    const state = reactive({ //Dados Reativos
      moedas: {},
    })

    onMounted(async () => {
      const response = await api.all('/all/USD-BRL,EUR-BRL,BTC-BRL,ETH-BRL')
      state.moedas = response.data
    })

    return {
      ...toRefs(state)
    }
  }}

</script>

<style>
  .h4{
    text-align: center;
    margin-bottom: 10px;
  }
  .card{
    box-shadow: inset 0 0 1em grey, 0 0 1em #000;
  }
</style>
