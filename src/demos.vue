<template>
  <section class="page-demo">
    <div v-for="group in navs">
      <div class="page-title" v-text="group.title"></div>
      <mt-cell
        v-for="item in group.list"
        v-link="{ path: item.path }"
        is-link>
        <div slot="title">
          <i class="indexicon icon-{{ item.icon }}"></i>
          <span>{{ item.name }}</span>
        </div>
      </mt-cell>
    </div>
  </section>
</template>

<style lang="scss">
  .page-demo {
    padding-bottom: 50px;

    .indexicon {
      font-size: 22px;
      color: #26a2ff;
      display: inline-block;
      width: 30px;
      vertical-align: middle;

      &.icon-swipe {
        font-size: 26px;
      }

      &.icon-checklist {
        font-size: 18px;
      }
    }
  }

  .page-title {
    font-size: 20px;
    margin: 20px auto;
    text-align: center;
    display: block;
    line-height: 1;
  }

  .page-part {
    margin-bottom: 15px;
  }
</style>

<script type="text/babel">
  import { navs } from './route';

  export default {
    data() {
      return {
        navs: []
      };
    },

    compiled() {
      this.navs = navs;
    }
  };
</script>
