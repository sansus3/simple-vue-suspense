<template>
    
<div class="w-full max-w-sm bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700 p-5 m-auto">
    <div class="flex flex-col items-center">
        <img class="mb-3 w-24 h-24 rounded-full shadow-lg" :src="user.picture.medium" alt="Bonnie image">
        <h5 class="mb-1 text-xl font-medium text-gray-900 dark:text-white">{{name.title}} {{name.first}} {{name.last}}</h5>
        <span class="text-sm text-gray-500 dark:text-gray-400">{{user.email}}</span>
    </div>
</div>


</template>

<script setup>
import { reactive, toRefs } from 'vue';
const res = await fetch('https://randomuser.me/api');
const {results} = await res.json();
const user = reactive(results[0]);
const {name} = toRefs(user);//Desestructuro y mantengo reactividad
console.log(user)
</script>