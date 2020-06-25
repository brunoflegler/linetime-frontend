<template>
  <div>
    <Header/>
    <RangeSlider> </RangeSlider>
  </div>
</template>

<script>
import Header from '@/components/Header'
import RangeSlider from '@/components/RangeSlider'

export default {
  name: 'TimelineView',
  components: {
    Header,
    RangeSlider
  }
}
</script>
