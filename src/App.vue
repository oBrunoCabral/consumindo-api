<template>
  <v-app style="background-color: #66BB6A">
    <Home/>
  </v-app>
</template>

<script>
import Home from './components/Home';

export default {
  name: 'App',
  components: {
    Home,
  },
  data: () => ({
    //
  }),
};
</script>

<style>
* {
 box-sizing: border-box;
}
*:before,
*:after {
 box-sizing: border-box;
}
html,
body {
 height: 100%;
 position: relative;
}
#main-div {
 min-height: 100vh; /* will cover the 100% of viewport */
 overflow: hidden;
 display: block;
 position: relative;
 
}
#footer {
 position: absolute;
 bottom: 0;
 width: 100%;
 color: black;
}
</style>