<template>
  <a class="mint-tab-item"
    @click="$parent.selected = id"
    :class="{ 'is-selected': $parent.selected === id }">
    <div class="mint-tab-item-icon"><slot name="icon"></slot></div>
    <div class="mint-tab-item-label"><slot></slot></div>
  </a>
</template>

<script>
/**
 * mt-tab-item
 * @module components/tab-item
 * @desc 搭配 tabbar 或 navbar 使用
 * @param {*} id - 选中后的返回值，任意类型
 * @param {slot} [icon] - icon 图标
 * @param {slot} - 文字
 *
 * @example
 * <mt-tab-item>
 *   <img slot="icon" src="http://placehold.it/100x100">
 *   订单
 * </mt-tab-item>
 */
export default {
  name: 'mt-tab-item',

  props: {
    id: ''
  }
};
</script>

<style lang="scss">
  @import "../../../style/var.scss";

  .mint-tab-item {
    display: block;
    padding: 7px 0;
    flex: 1;

    .mint-tab-item-icon {
      size: 24px;
      margin: 0 auto 5px;

      &:empty {
        display: none;
      }

      & > * {
        display: block;
        size: 100%;
      }
    }

    .mint-tab-item-label {
      color: inherit;
      font-size: $tab-item-font-size;
      line-height: 1;
    }
  }
</style>
