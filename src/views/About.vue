<template>
  <div class="about">
    <Titulo :contador="contador" />
    <h1
    :style="{'color': color}"
    >Countdown: {{contador}}</h1>
    <button @click="aumentar">+</button>
    <button @click="disminuir">-</button>
    <hr>
    <input type="text" v-model="texto">
    <p>{{texto}}</p>
  </div>
</template>

<script>
import { ref, computed } from '@vue/reactivity'
import Titulo from '../components/Titulo.vue'

export default {
  components: {
    Titulo,
  },
  setup() {
    const contador = ref(0);

    const aumentar = () => {
      contador.value ++
    }
    const disminuir = () => {
      contador.value --
    }
    
    const color = computed(() => {
      if(contador.value < 0){
        return 'red'
      } else {
        return 'blue'
      }
    })

    const texto = ref('');

    return {contador, aumentar, disminuir, color, texto}
  },
}
</script>