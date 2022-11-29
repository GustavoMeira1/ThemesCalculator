<template>
  <v-app>
      <calc/>
  </v-app>
</template>

<script>
import calc from './components/calc';

export default {
  name: 'App',

  components: {
    calc,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@700&display=swap');
#app{
  background-color: hsl(222, 26%, 31%);
  font-family: 'League Spartan', sans-serif;
}
</style>
