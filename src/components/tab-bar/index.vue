<template>
  <ul class="tabbar-wrapper">
    <li
      v-for="(tab, index) in list"
      :key="tab.name"
      @click="onClick(index)"
      :class="{ active: currentTab === index }"
    >
      <i class="iconfont" :class="tab.icon" />
      <span class="tab-name">{{ tab.name }}</span>
    </li>
  </ul>
</template>

<script>
import { ref } from 'vue';

const useTabBar = () => {
  const currentTab = ref(0);
  const list = [
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
  ];

  const onClick = (index) => {
    currentTab.value = index;
  };

  return {
    list,
    currentTab,
    onClick
  };
};

export default {
  name: 'Tabbar',

  setup() {
    const { list, currentTab, onClick } = useTabBar();

    return {
      list,
      currentTab,
      onClick
    };
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
  margin: 0;
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
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    justify-content: center;
    i {
      font-size: 0.2rem;
    }

    &.active {
      color: #1fa4fc;
    }

    .tab-name {
      line-height: 0.14rem;
    }
  }
}
</style>
