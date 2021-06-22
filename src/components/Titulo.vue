<template>
<h2
:style="{'color': color}"
>Contador: {{signoDolar}}</h2>
</template>

<script>
import { computed } from '@vue/runtime-core'
export default {
    props: ['contador', 'color'],
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
