<template>
  <v-app light>
    <v-toolbar
      fixed
      app
    >
      <v-btn
        icon
        @click="moveToAnchor(`${up}`)"
      >
        <v-icon left>
          thumb_down_alt
        </v-icon>
        Down
      </v-btn>
      <v-spacer />
      <v-btn
        icon
        @click="moveToAnchor(`${down}`)"
      >
        <v-icon left>
          thumb_up_alt
        </v-icon>
        Up
      </v-btn>
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      up: 'up',
      down: 'down'
    }
  },
  methods: {
    moveToAnchor(hashbang) {
      this.$router.push(`#${hashbang}`)
      this.$vuetify.goTo(`#${hashbang}`)
      console.log(this.$route.hash)
    }
  }
}
</script>
