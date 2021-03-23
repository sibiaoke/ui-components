<template>
  <div class="action">
    <slot></slot>
  </div>
</template>

<style lang="scss" scoped>
.action {
    cursor: pointer;
    opacity: 0.8;
    margin-left: 14px;

    &:hover {
      opacity: 1;
    }
  }
</style>
