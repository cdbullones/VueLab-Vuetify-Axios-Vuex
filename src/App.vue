<template>
  <v-app>
    <v-content>
      <v-container>
          <router-view/>
          <v-dialog
            v-model="loading.estado"
            hide-overlay
            persistent
            width="300"
          >
            <v-card
              :color="loading.color"
              dark
            >
              <v-card-text>
                {{loading.titulo}}
                <v-progress-linear
                  indeterminate
                  color="white"
                  class="mb-0"
                ></v-progress-linear>
              </v-card-text>
            </v-card>
          </v-dialog>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>

import { mapState } from "vuex";

export default {
  name: 'App',
  data () {
    return {
      //
    }
  },
  computed:{
    ...mapState(['loading'])
  }
}
</script>
