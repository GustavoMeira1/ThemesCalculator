<template>
  <v-app>
      <calc @index="getIndex"/>
  </v-app>
</template>

<script>
import calc from './components/calc';

export default {
  name: 'App',
  components: {
    calc,
  }, 
  methods: {
    getIndex(value) {
    if (value == 0) {
      document.getElementById("app").style.backgroundColor = "hsl(222, 26%, 31%)";
    } else if (value == 1) {
      document.getElementById("app").style.backgroundColor = "hsl(0, 0%, 90%)";
    } else {
      document.getElementById("app").style.backgroundColor = "hsl(268, 75%, 9%)";
   }
 }
}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@700&display=swap');

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app{
  background-color: hsl(222, 26%, 31%);
  font-family: 'League Spartan', sans-serif;
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
