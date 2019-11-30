<template>
  <v-layout>
    <v-flex xs6 offset-xs3>
      <panel title="Bem-vindo!">
        Para testar o programa em execução realize o cadastro.
      </panel>
    </v-flex>
  </v-layout>
</template>

<script>
import Panel from '@/components/Panel'
export default {
  components: {
    Panel
  },
  methods: {
    navigateTo (route) {
      this.$router.push(route)
    }
  }
}
</script>

<style scoped>
</style>
