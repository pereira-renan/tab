<template>
  <v-layout>
    <v-flex xs6 offset-xs3 v-if="$store.state.isUserLoggedIn">
      <panel title="Acesso autorizado">
        Você está logado e tem acesso completo ao conteúdo dessa página.
      </panel>
    </v-flex>
    <v-flex xs6 offset-xs3 v-if="!$store.state.isUserLoggedIn">
      <panel title="Acesso negado">
        Você precisa estar logado para acessar ao conteúdo dessa página.
      </panel>
    </v-flex>
  </v-layout>
</template>

<script>
import Panel from '@/components/Panel'
import SongsService from '@/services/SongsService'
export default {
  components: {
    Panel
  },
  data () {
    return {
      songs: null
    }
  },
  async mounted () {
    this.songs = (await SongsService.index()).data
  },
  methods: {
    navigateTo (route) {
      this.$router.push(route)
    }
  }
}
</script>

<style scoped>
.element {
  background-color: green;
}
</style>
