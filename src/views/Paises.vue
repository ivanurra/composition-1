<template>
  <h1>Lista de países:</h1>
  <p
  v-for="(pais, index) in arrayData" :key="index"
  >
  {{pais.name}}
  <br />
  Capital: {{pais.capital}}
  <br />
  Region: {{pais.region}}
  <br />
  <img src="pais.flag" alt="flag">
  <br />
  <br />
  </p>
</template>

<script>
import { ref } from '@vue/reactivity'
export default {
    setup(){
        const arrayData = ref([])

        const fetchData = async() => {
            try {
                const res = await fetch('https://restcountries.eu/rest/v2/all')
                arrayData.value = await res.json()
            } catch (error) {
                console.log(error)
            }
        }
        fetchData()

        return {arrayData}
    }
}
</script>
