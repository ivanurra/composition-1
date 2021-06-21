<template>
  <div class="home">
    <h2>Contador: {{contador}}</h2>
    <button @click="aumentar">+</button>
    <button @click="disminuir">-</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contador: 0
    }
  },
  methods: {
    aumentar(){
      this.contador++
    },
    disminuir(){
      this.contador--
    }
  }
}
</script>
