<script setup>
import { ref } from "vue";
    const color = ref('bg-green-500')
    const arr= ref([]);
    const data= ref("");
    const sh = ref("true")
    function add(params) {
        arr.value.push(data.value)
    }
    function hidd(params) {
        if (sh.value == true) {
            sh.value = false;
            color.value = 'bg-red-500'
        }else{
            sh.value = true;
            color.value = 'bg-green-500'
        }

    }

</script>
<template>
    <div class="flex justify-center mx-auto mt-36 bg-neutral-300 w-[500px] h-[500px] rounded">
        <div class="">
            <h1 class="text-center">Caja de Tareas</h1>
            <input type="text" v-model="data">
            <div class="flex justify-center ">
                <button class="border-2 bg-teal-600 text-white p-2 mr-8" @click="add">add</button>
                <button :class="['border-2 text-white p-2' , color]"  @click="hidd">hidden</button>
            </div>
            <div>
                <div v-for="(item,index) in arr" :key="index" v-show="sh">
                    {{index +1}} {{ item }}
                </div>
            </div>
        </div>
    </div>
</template>
