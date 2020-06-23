<template>
  <div class="main-slider">
    <div class="content d-flex align-center" >
        <v-range-slider v-model="epoch" :min="min" :max="max"></v-range-slider>
    </div>
    <pre>{{$data}}</pre>
  </div>
</template>

<script>
import moment from 'moment'

export default {
  name: 'RangeSlider',
  data: () => ({ min: 0, max: 0, epoch: [0, 0] }),
  watch: {
    epoch ([epoch1, epoch2]) {
      if (epoch1 === this.min || epoch2 === this.max) {
        this.min = moment(this.min).subtract(7, 'days').valueOf()
        this.max = moment(this.max).add(7, 'days').valueOf()
      }
    }
  },
  mounted () {
    this.min = moment().subtract(7, 'days').valueOf()
    this.max = moment().add(7, 'days').valueOf()
    this.epoch = [moment().startOf('day').valueOf(), moment().valueOf()]
  }
}
</script>
<style>
  .main-slider {
    padding-top: 50px;
    height: 300px;
  }

  .main-slider .content {
    height: 100%;
    background: #ffffff;
  }
</style>
