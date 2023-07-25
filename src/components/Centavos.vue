<template>
  
       <div class="table">
        <thead>
            <tr>

                <th>Código</th>
                <th>Nome</th>
                <th>Máximo</th>
                <th>Minimo</th>
                <th>Variação</th>
                <th>Data</th>

                <th></th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(moeda, key) in moedas" :key="key">
                <td>{{ key }}</td>
                <td>{{ moeda.name }}</td>
                <td>{{ moeda.high }}</td>
                <td>{{ moeda.low }}</td>
                <td>{{ moeda.varBid }}</td>
                <td>{{ moeda.create_date }}</td>
            </tr>
        </tbody>
       </div>

</template>

<script>
export default {
    props:{moedas: {type: Object, required: true}},
    name: 'Centavos',
    data() {
        return {
          
        }
    }
}
</script>

<style>

</style>