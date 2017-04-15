<template>
  <div class="Workout">
    <div class="Workout Workout-name">{{currentTimer.name}}</div>
    <div class="Workout Workout-duration">{{currentTimer.duration}}</div>
    <button v-on:click="togglePlay">Start workout</button>
    <div class="round" v-for="round in currentTimer.rounds">
      {{round.name}} | {{round.type}} | {{round.duration}}
    </div>
  </list>
  </div>
</template>

<script>
import timers from '@/mocks/timers'

export default {
  name: 'workout',
  props: ['id'],
  data () {
    return {
      timers: timers,
      isPlaying: false
    }
  },
  computed: {
    currentTimer () {
      return this.timers.find(t => t.id === parseInt(this.id))
    },
    /**
     * Don't repeat yourself, mister.
     * @TODO: Have this as part of the timer model when migrating to
     * vue-model
     */
    totalDuration () {
      let total = 0

      for (let i = 0; i < this.currentTimer.rounds.length; i++) {
        let round = this.currentTimer.rounds[i]
        total += round.duration
      }

      return total
    }
  },

  methods: {
    togglePlay () {
      console.log('The play would be toggled.')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
