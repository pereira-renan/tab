<template>
  <v-toolbar fixed class="cyan" dark>
    <v-toolbar-side-icon></v-toolbar-side-icon>
      <v-toolbar-title class ="mr-4">
        IBM Brasil - Customer Relationship Manager
      </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat
          @click="navigateTo({ name: 'register' })">
            Signup
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
</style>
