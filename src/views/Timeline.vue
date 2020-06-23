<template>
  <div>
    <Header name="Timeline" description="Data e hora atual é 1592780034 em millesegundos"/>
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
