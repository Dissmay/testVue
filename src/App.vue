<template>
 <v-app>
  <HelloWorld/>
  <Carousel/>
 </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import Carousel from './components/carousel'
export default {
  name: 'App',
  components: {
    HelloWorld,
    Carousel
  },
  data: () => ({
    //
  }),
};
</script>
