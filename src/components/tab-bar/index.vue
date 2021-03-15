<template>
  <ul class="tabbar-wrapper">
    <li
      v-for="(tab, index) in list"
      :key="tab.name"
      @click="onClick(index)"
      :class="{ active: currentTab === index }"
    >
      <i class="iconfont" :class="tab.icon" />
      {{ tab.name }}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'Tabbar',

  data() {
    return {
      list: [
        {
          icon: 'icon-shouye',
          name: '首页'
        },
        {
          icon: 'icon-gouwuche',
          name: '购物车'
        },
        {
          icon: 'icon-wodedingdan',
          name: '订单'
        },
        {
          icon: 'icon-wodejuhuasuan',
          name: '我的'
        }
      ],
      currentTab: 0
    };
  },

  methods: {
    onClick(index) {
      this.currentTab = index;
    }
  }
};
</script>

<style lang="scss">
.tabbar-wrapper {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  height: 0.5rem;
  box-shadow: 0 -1px 1px 0 #f1f1f1;
  box-sizing: border-box;
  padding: 0 0.4rem;
  list-style: none;

  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  align-items: center;

  li {
    display: flex;
    flex-flow: column nowrap;
    color: #333;
    font-size: 0.1rem;
    text-align: center;
    i {
      padding-bottom: 5px;
      font-size: 0.2rem;
    }

    &.active {
      color: #1fa4fc;
    }
  }
}
</style>
