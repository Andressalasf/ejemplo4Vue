<script setup>
  import TaskComponent  from '@/components/TaskComponent.vue';
  import { ref } from 'vue';

  const tareas = ref(['Estudiar',  'Sacar 5', 'Descansar'])

  function deleteTask(index){
    // console.log('borrar hijo', index)
    tareas.value.splice(index, 1)
  }

</script>

<template>
  <div class="bg-gray-50 w-96 shadow-md rounded-md my-0 mx-auto mt-12 p-4">
      <h1 class=" text-2xl font-semibold"> Tarea </h1>
      <div class=" flex mt-4 mb-2">
          <input class=" rounded-r-none w-4/5 h-8 px-2 border rounded-md  py-1 border-purple-400 outline-none" type="text">
          <span class=" hover:bg-purple-600 cursor-pointer text-center rounded-l-none rounded-r-md text-white w-1/5 h-8 text-xl bg-purple-500">+</span>
      </div>
    <TaskComponent
      v-for="(task, index) in tareas" :key="index" :tarea = "task" :index = "index" @borrarTarea="deleteTask"/>
  </div>
  
    
</template>

<style scoped></style>
