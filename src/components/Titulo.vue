<template>
<h2>Contador: {{signoDolar}}</h2>
</template>

<script>
import { computed } from '@vue/runtime-core'
export default {
    props: ['contador'],
    // computed: {
    //     signoDolar(){
    //         return '$' + this.contador
    //     }
    // }
    setup(props){
        const signoDolar = computed(() => {
            return '$' + props.contador
        })

        return {signoDolar}
    }
}
</script>
