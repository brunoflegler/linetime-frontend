<template>
 <v-app>
  <v-main class="ma-0 pa-0">
    <v-container class="ma-0 pa-0" fluid>
      <Timeline />
    </v-container>
  </v-main>
 </v-app>
</template>

<script>
import Timeline from './views/Timeline'

export default {
  name: 'App',
  components: {
    Timeline
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

input,
button {
  outline: 0;
}

.v-main {
  background: #f5f5f5 !important;
  font-family: "Helvetica Neue", "Helvetica", Arial, sans-serif;
  text-rendering: optimizeLegibility !important;
  -webkit-font-smoothing: antialiased !important;
}

.content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 30px;
}
</style>
