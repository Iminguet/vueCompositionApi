<template>
  <section class="container">
    <h2>{{ user.name }}</h2>
    <h3>{{ user.age }}</h3>
    <h3>{{ user }}</h3>
  </section>
</template>
<!-- 

  *** EL MÉTODO SETUP PUEDE SER REEMPLAZADO POR ESTA FORMA ***
<script setup>
import { ref } from 'vue';
 
const uName = ref('Maximilian');
 
setTimeout(function() {
  uName.value = 'Max';
}, 2000);
</script> -->

<script>
import { ref } from 'vue';
// ref es reactivo
export default {
  setup() {
    // const uName = ref('Aureliano');
    // const uAge = ref(40);

    const user = ref({
      name: 'Aureliano',
      age: 40,
    });

    setTimeout(() => {
      // debemos usar el .value si SOLO queremos modificar el valor
      user.value.name = 'Sr. Buendía';
      user.value.age = 41;
    }, 3000);

    return { userName: user.value.name, age: user.value.age, user: user };
  },

  // data() {
  //   return {
  //     userName: 'Maximilian',
  //   };
  // },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
