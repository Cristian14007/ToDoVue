<script setup lang ="ts">
import {ref} from 'vue';


//const counter = ref(0); //reactive
const props = defineProps<{
    name:string,
    counter:number
}>();
// const props = defineProps(['name','counter'])
const emit = defineEmits(['increment'])

</script>
<template>


    <div>Hola {{ name }}!!</div>
    <div>El valor del contador es {{ counter }}</div>
    <div><button @click="emit('increment')">Increment</button></div>


</template>