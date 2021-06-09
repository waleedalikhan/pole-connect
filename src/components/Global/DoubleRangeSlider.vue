<template>
  <div class="content">
    <div
      :id="sliderId"
      :se-min="minThreshold"
      :se-step="step"
      :se-min-value="min"
      :se-max-value="max"
      :se-max="maxThreshold"
      class="slider"
    >
      <div class="slider-touch-left -mt-6">
        {{ min }}
        <span></span>
      </div>
      <div class="slider-touch-right -mt-6">
        {{ max }}
        <span></span>
      </div>
      <div class="slider-line">
        <span></span>
      </div>
    </div>
  </div>
</template>

<script>
import DoubleSlider from '@/util/doubleSlider'

export default {
  props: {
    sliderId: String,
    minThreshold: {
      type: Number,
      default: -100,
    },
    maxThreshold: {
      type: Number,
      default: 100,
    },
    step: {
      type: Number,
      default: 1,
    },
    min: {
      type: Number,
      required: true,
    },
    max: {
      type: Number,
      required: true,
    },
  },
  data: function() {
    return {
      instance: undefined,
    }
  },
  mounted: function() {
    this.instance = new DoubleSlider(this.sliderId)
    this.instance.onChange = (min, max) => this.updateValues(min, max)
  },
  destroyed: function() {},
  methods: {
    updateValues: function(min, max) {
      this.$emit('update:min', min)
      this.$emit('update:max', max)
    },
  },
}
</script>

<style>
.slider {
  display: block;
  position: relative;
  height: 36px;
  width: 100%;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  -o-user-select: none;
  user-select: none;
}
.slider .slider-touch-left,
.slider .slider-touch-right {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  display: block;
  position: absolute;
  height: 36px;
  width: 36px;
  padding: 6px;
  z-index: 2;
}
.slider .slider-touch-left span,
.slider .slider-touch-right span {
  display: block;
  width: 26px;
  height: 26px;
  background: #CDD8E2;
  border: 1px solid #CDD8E2;
  border-radius: 50%;
}
.slider .slider-line {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  position: absolute;
  width: calc(100% - 36px);
  left: 18px;
  top: 16px;
  height: 4px;
  border-radius: 4px;
  background: #DBDBDB;
  z-index: 0;
  overflow: hidden;
}
.slider .slider-line span {
  display: block;
  height: 100%;
  width: 0%;
  background: #00437C;
}
</style>