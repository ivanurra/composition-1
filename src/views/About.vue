<template>
  <div class="about">
    <h1
    :style="{'color': color}"
    >Countdown: {{contador}}</h1>
    <button @click="aumentar">+</button>
    <button @click="disminuir">-</button>
  </div>
</template>

<script>
import { ref, computed } from '@vue/reactivity'
export default {
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

    return {contador, aumentar, disminuir, color}
  },
}
</script>