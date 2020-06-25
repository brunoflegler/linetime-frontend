<template>
  <header class="main-header">
    <div class="content">
      <h1>LineTime</h1>
      <div>
        <nav>Data e hora atual é {{currentDate}} em millesegundos</nav>
      </div>
    </div>
  </header>
</template>

<script>
import moment from 'moment'

export default {
  props: ['name', 'description'],
  data: () => ({ currentDate: 0 }),
  methods: {
    updateCurrentDate () {
      this.currentDate = moment().valueOf()
    }
  },
  mounted () {
    this.currentDate = moment().valueOf()
    this.intervalValue = setInterval(this.updateCurrentDate, 1000)
  },
  destroyed () {
    clearInterval(this.intervalValue)
  }
}
</script>

<style scoped>
  .main-header {
    height: 150px;
    background: #4267b2;
    position: relative;
    z-index: 1;
  }

  .main-header .content {
    display: flex;
    flex-direction: column;
    align-items: left;
    justify-content: center;
    height: 100%;
  }

  .main-header .content h1 {
    color: #ffffff;
    font-size: 40px;
  }

  .main-header .content nav {
    color: lightgrey;
    font-size: 12px;
    font-style: italic;
  }
</style>
