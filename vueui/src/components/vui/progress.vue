<template>
  <div class="displayBar">
    <div class="displayBarFill" :style="{ width: percentage + '%'}"><span><slot/></span></div>
  </div>
</template>

<script>
export default {
  name: 'vui-progress',
  props: {
    value: {
      type: Number,
      default: 50
    },
    max: {
      type: Number,
      default: 100
    },
    min: {
      type: Number,
      default: 0
    }
  },
  computed: {
    percentage() {
      return (this.value - this.min) / (this.max - this.min) * 100
    }
  }
}
</script>

<style lang="scss" scoped>
  .displayBarFill {
    line-height: 1em;
    white-space: nowrap;
    overflow: visible;
    span {
      vertical-align: middle;
      margin-left: 2px;
    }
  }
</style>
