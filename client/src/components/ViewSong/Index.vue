<template>
  <div>
    <v-flex xs6>
      <song-metadata :song="song"/>
    </v-flex>
    <v-layout>
      <v-flex xs6>
        <panel title="song metadata">
          <textarea
            readonly
            v-model="song.lyrics"
          ></textarea>
        </panel>
      </v-flex>
      <v-flex xs6>
        <panel title="lyrics" class="ml-2">
          <textarea
            readonly
            v-model="song.tab"
          ></textarea>
        </panel>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import SongMetadata from './SongMetadata'
import SongsService from '@/services/SongsService'
import Panel from '@/components/Panel'

export default {
  data () {
    return {
      song: {}
    }
  },
  async mounted () {
    const songId = this.$store.state.route.params.songId
    this.song = (await SongsService.show(songId)).data
  },
  components: {
    Panel,
    SongMetadata
  },
  methods: {
    navigateTo (route) {
      this.$router.push(route)
    }
  }
}
</script>

<style scoped>
textarea {
  width: 100%;
  border: none;
  height: 600px;
  border-style: none;
  border-color: none;
  overflow: auto;
  padding: 40px;
}
</style>
