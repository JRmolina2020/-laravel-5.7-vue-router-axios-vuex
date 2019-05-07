<template>
  <v-card height="500px">
    <v-container>
      <slot name="contenido"></slot>
    </v-container>
    <v-bottom-nav :active.sync="bottomNav" :color="color" :value="true" absolute dark shift>
      <v-btn dark to="/">
        <span>Video</span>
        <v-icon>ondemand_video</v-icon>
      </v-btn>

      <v-btn dark to="/about">
        <span>Music</span>
        <v-icon>music_note</v-icon>
      </v-btn>
    </v-bottom-nav>
  </v-card>
</template>
<script>
export default {
  data() {
    return {
      bottomNav: 3
    };
  },

  computed: {
    color() {
      switch (this.bottomNav) {
        case 0:
          return "blue-grey";
        case 1:
          return "teal";
        case 2:
          return "brown";
        case 3:
          return "indigo";
      }
    }
  }
};
</script>
