<template>
  <v-toolbar fixed class="red" dark>
    <!-- <v-toolbar-side-icon></v-toolbar-side-icon> -->
      <v-toolbar-title class ="mr-4">
        <v-btn
          flat
          dark
          @click="navigateTo({ name: 'home' })">
          Home
        </v-btn>
      </v-toolbar-title>
        <v-btn
          v-if="$store.state.isUserLoggedIn"
          flat
          dark
          @click="navigateTo({ name: 'songs' })">
          Browse
        </v-btn>
    <v-spacer></v-spacer>
        <v-btn
          v-if="!$store.state.isUserLoggedIn"
          flat
          dark
          @click="navigateTo({ name: 'login' })">
          Login
        </v-btn>
        <v-btn
          v-if="!$store.state.isUserLoggedIn"
          flat
          dark
          @click="navigateTo({ name: 'register' })">
            Sign Up
        </v-btn>
        <v-btn
          v-if="$store.state.isUserLoggedIn"
          flat
          dark
          @click="logout">
            Log Out
        </v-btn>
  </v-toolbar>
</template>

<script>
export default {
  methods: {
    navigateTo (route) {
      this.$router.push(route)
    },
    logout () {
      this.$store.dispatch('setToken', null)
      this.$store.dispatch('setUser', null)
      this.$router.push({ name: 'home' })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home {
  cursor: pointer;
}
.v-btn:hover {
  background-color: #fff;
  color: #000;
}
</style>
