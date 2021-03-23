<template>
  <svg :class="svgClass" aria-hidden="true" @click="$emit('click')">
    <use :xlink:href="iconName" />
  </svg>
</template>

<script>
export default {
  name: 'SvgIcon',
  props: {
    iconClass: {
      type: String,
      required: true
    },
    className: {
      type: String,
      default: ''
    },
    btn: Boolean
  },
  computed: {
    iconName() {
      return `#icon-${this.iconClass}`
    },
    svgClass() {
      let cls = 'svg-icon'
      if (this.btn) {
        cls += ' svg-btn'
      }
      if (this.className) {
        cls += ` ${this.className}`
      }
      return cls
    }
  }
}
</script>

<style scoped lang="scss">
@import '~@sibiaoke/ui-theme/src/mixins/themes';

$svg-theme: (
  light: (
    color-bg: $light-border-color-base
  ),
  dark: (
    color-bg: $dark-border-color-base
  )
);

.svg-icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;

  &.svg-btn {
    cursor: pointer;
    border-radius: 50%;
    padding: 4px;
    font-size: 20px;
    align-self: center;
    vertical-align: middle;

    &:hover {
      @include themify($svg-theme) {
        background: themed('color-bg');
      }
    }
  }
}
</style>
