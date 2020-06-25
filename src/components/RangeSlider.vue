<template>
  <div class="main-slider">
    <div class="content" >
        <div class="container-header">
          <div class="d-flex flex-column">
            <label class="label-format">{{startDateFormatLabel}}</label>
            <label class="label-epoch">{{epoch[0]}}</label>
          </div>
          <div class="d-flex flex-column">
            <label class="label-format">{{endDateFormatLabel}}</label>
             <label class="label-epoch">{{epoch[1]}}</label>
          </div>
        </div>
        <div>
          <v-range-slider v-model="epoch"  :min="minDateEpoch" :max="maxDateEpoch"></v-range-slider>
        </div>
    </div>
  </div>
</template>

<script>
import moment from 'moment'

export default {
  name: 'RangeSlider',
  data: () => ({
    minDateEpoch: 0,
    maxDateEpoch: 0,
    epoch: [0, 0]
  }),
  computed: {
    startDateFormatLabel () { return moment(this.epoch[0]).format('DD/MM/YYYY HH:mm:ss') },
    endDateFormatLabel () { return moment(this.epoch[1]).format('DD/MM/YYYY HH:mm:ss') }
  },
  watch: {
    epoch ([startDateEpoch, endDateEpoch]) {
      if (startDateEpoch === this.minDateEpoch || endDateEpoch === this.maxDateEpoch) {
        this.minDateEpoch = moment(this.minDateEpoch).subtract(1, 'days').valueOf()
        this.maxDateEpoch = moment(this.maxDateEpoch).add(1, 'days').valueOf()
      }
    }
  },
  mounted () {
    this.minDateEpoch = moment().subtract(7, 'days').valueOf()
    this.maxDateEpoch = moment().add(7, 'days').valueOf()
    this.epoch = [moment().startOf('day').valueOf(), moment().valueOf()]
  }
}
</script>

<style>
  .main-slider {
    padding-top: 50px;
  }

  .main-slider .content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    background: #ffffff;
    height: 300px;
  }

  .main-slider .content .container-header {
    display: flex;
    justify-content: space-between;
    padding: 0 70px 20px 70px;
  }

  .main-slider .content .container-header .label-format {
    font-weight: bold;
  }

  .main-slider .content .container-header .label-epoch {
    font-size: 12px;
    color: gray;
  }

</style>
