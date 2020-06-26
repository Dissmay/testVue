<template>
  <v-card
    class="mx-auto"
    max-width="203"
    >
    <v-img
      class="red--text align-end"
      height="150px"
      src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      >
    </v-img>
    <v-card-text class="text--primary">
      <div>Whitsunday Island</div>
    </v-card-text>

    <v-card-actions>
      <v-btn color="green" text>
        Add to cart
        <v-icon right>
          mdi-cart-arrow-up
        </v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template>


<script>
  export default {
    data: () => ({
      
    }),
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
