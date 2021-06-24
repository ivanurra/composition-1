<template>
  <!-- <h1>Info about {{$route.params.nombre}}</h1> -->
  <h1>Info about {{nombre}}</h1>
</template>

<script>
import {useRoute} from 'vue-router'
export default {
    props: ['nombre'],
    setup(props) {
        const nombreParams = useRoute()
    }
}
</script>
