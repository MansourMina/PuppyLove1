<template>
  <v-app>
    <v-app-bar app color="brown" dark>
      <div class="d-flex align-center">
        <v-img
          id="logo"
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="puppy.png"
          transition="scale-transition"
          width="70"
        />

        <span class="text-h4"
          >Puppy Love <v-icon large color="green">mdi-heart-outline</v-icon>
        </span>
      </div>
      <v-spacer></v-spacer>

      <div class=" mr-2">
        <v-btn  plain to="/"><v-icon>mdi-home-outline</v-icon>HOME</v-btn>
      </div>
      <div class=" mr-2">
        <v-btn  plain to="/about"><v-icon>mdi-account</v-icon>ABOUT</v-btn>
      </div>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>

<style scoped>
#logo {
  margin-top: 20px;
}

</style>
