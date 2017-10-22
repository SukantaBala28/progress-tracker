<template>
  <li class="progress-step" :class="{ 'is-active': isActive, 'is-complete': isComplete }">
    <span class="progress-marker">{{ marker }}</span>
    <span class="progress-text" v-if="title">
      <h4 class="progress-title">{{ title }}</h4>{{ text }}
      <slot></slot>
    </span>
  </li>
</template>

<script>
export default {
  props: {
    isActive: Boolean,
    isComplete: Boolean,
    marker: {
      type: String,
      default: ''
    },
    kind: String,
    title: String,
    text: String
  },

  created () {
    this._isStepItem = true
  },

  computed: {
    index () {
      return this.$parent.$stepItems.indexOf(this)
    }
  }

}
</script>
<style>
 .progress-marker {
  border-radius: 0%!important;
  width:50px!important;
  height:30px!important;
 }
</style>
