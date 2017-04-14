<template>
  <div class="hello Dashboard">
    <list
      :items=timers
    >
  </list>
  </div>
</template>

<script>
export default {
  name: 'dashboard',
  data () {
    return {
      timers: [{
        name: 'Timer 1',
        rounds: [{
          name: 'Round 1',
          duration: 120,
          type: 'workout'
        }, {
          name: 'Round 2',
          duration: 30,
          type: 'break'
        }, {
          name: 'Round 3',
          duration: 120,
          type: 'workout'
        }]
      },
      {
        name: 'Timer 2',
        rounds: [{
          name: 'Round 1',
          duration: 120,
          type: 'workout'
        }, {
          name: 'Round 2',
          duration: 30,
          type: 'break'
        }, {
          name: 'Round 3',
          duration: 150,
          type: 'workout'
        }]
      }]
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
