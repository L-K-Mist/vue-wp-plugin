<template>
  <v-app id="vue-backend-app">
    <v-card>
      <v-card-text>
        <h1>Backend App</h1>

        <router-view />
      </v-card-text>
    </v-card>
  </v-app>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
</style>
