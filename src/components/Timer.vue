<template>
	<v-container fluid>
    <v-layout>
      <v-flex xs12 pa-3>
        <v-card>
          <v-card-title class="secondary white--text font-weight-light display-2 text-uppercase justify-center">
            {{ timer }}
          </v-card-title>
          <v-card-text>
            <v-list>
              <v-list-tile
                class="success mb-3"
                @click="$emit('start')"
                :disabled="state == 'running'"
              >
                <span class="white--text font-weight-bold text-uppercase">Start</span>
              </v-list-tile>
              <v-list-tile
                class="info mb-3"
                @click="$emit('lap')"
                :disabled="state == 'stopped' || state == 'paused'"
              >
                <span class="white--text font-weight-bold text-uppercase">Lap</span>
              </v-list-tile>
              <v-list-tile
                class="warning mb-3"
                @click="$emit('pause')"
                :disabled="state == 'stopped' || state == 'paused'"
              >
                <span class="white--text font-weight-bold text-uppercase">Pause</span>
              </v-list-tile>
              <v-list-tile
                class="error"
                @click="$emit('stop')"
                :disabled="state == 'stopped'"
              >
                <span class="white--text font-weight-bold text-uppercase">Stop</span>
              </v-list-tile>
            </v-list>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'Timer',
  props: ['timer', 'state']
}
</script>
