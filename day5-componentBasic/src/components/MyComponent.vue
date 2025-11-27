<script setup>
import { ref } from 'vue';

    // // Declarin variable
    // const message = 'Hello World!';

    // // number
    // const variable = 10;

    // // 
    // const aBoolean = true;

    // // Object
    // const person = {firstName:"John", lastName:"Doe"};

    // // Array object
    // const cars = ["Saab", "Volvo", "BMW"];


    // const count = ref(0);

    // function increment(){
    //       count.value++
    // }

    const post = defineProps({
        title : String,
        content : String
    })
</script>

<template>
    <!-- <h1>{{ message }}</h1>
    <h2>{{ variable }}</h2>
    <h3>{{ aBoolean }}</h3>
    <h4>{{ person.firstName}}</h4>
    <h5>{{ cars[0] }}</h5> -->

    <!-- <button @click="increment">Click {{ count }}</button> -->

     <div class="post">
        <h3>{{ title }}</h3>
        <p>{{ content }}</p>
    </div>
</template>

<style scoped>
  
</style>
