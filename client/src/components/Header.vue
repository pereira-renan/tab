<template>
  <v-toolbar fixed class="cyan" dark>
    <!-- <v-toolbar-side-icon></v-toolbar-side-icon> -->
      <v-toolbar-title class ="mr-4">
        <span
        class="home"
        @click="navigateTo({ name: 'root' })">
        CRM
        </span>
      </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
          v-if="!$store.state.isUserLoggedIn"
          flat
          @click="navigateTo({ name: 'login' })">
          Login
        </v-btn>
        <v-btn
          v-if="!$store.state.isUserLoggedIn"
          flat
          @click="navigateTo({ name: 'register' })">
            Sign Up
        </v-btn>
      <v-btn flat>Link Two</v-btn>
      <v-btn flat>Link Three</v-btn>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>
export default {
  methods: {
    navigateTo (route) {
      this.$router.push(route)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home {
  cursor: pointer;
}
.home:hover {
  color: black;
}
</style>
