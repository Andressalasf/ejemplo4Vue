<script setup>
     const props =  defineProps({
        tarea: {
            type: String,
            default: 'Tarea indefinida'
        },
        index: {
            type: Number
        }
     })

     const emit = defineEmits(['borrarTarea'])

     function borrarTarea(index){
        // console.log('Borrar tarea')
        emit('borrarTarea', index)
     }
</script>
   
<template>
    <div class=" flex justify-between mt-1 bg-gray-200 rounded-md px-4 py-1">
        {{ props.tarea }}
         <span class=" hover:bg-red-700 cursor-pointer text-center  text-white px-2 text-xl rounded-md bg-red-500"
          @click="borrarTarea(props.index)">X</span>
    </div>
  </template>

