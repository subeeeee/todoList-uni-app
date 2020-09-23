<template>
  <view class="t-model-tltle">
    <slot name="title"></slot>
  </view>
</template>

<script>
  export default {
    name: 'model-title'
  }
</script>

<style scoped lang="scss">
  .t-model-tltle{
    font-size: $uni-font-size-base;
    background-color: #fff;
  }
</style>
