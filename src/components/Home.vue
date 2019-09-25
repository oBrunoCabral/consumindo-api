<template>
  <div id="main-div">
    <v-app-bar
      class="text--black"
      :color="color"
    >
      <v-toolbar-title>
        <v-icon>fas fa-radiation</v-icon>
      </v-toolbar-title>
      <div class="flex-grow-1"></div>
    </v-app-bar>
    <v-container>
      <CardPrincipal/>
    </v-container>
    <Footer />
  </div>
</template>

<script>
import CardPrincipal from '@/components/CardPrincipal'
import Footer from '@/components/Footer'

export default {
  name: 'Home',
  data: () => ({
    color:"#FFD600",
  }),
  components:{
    CardPrincipal,
    Footer,
  }
}
</script>

<style>

</style>