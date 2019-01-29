<template>
  <div class="page">
    <h1 v-if="title">{{ title }}</h1>
    <ul class="tabs" v-if="actualTabs">
      <li
        v-for="(tab, i) in actualTabs"
        :key="i"
        :class="{ 'is-active': tab.active }"
        class="tabs-component-tab"
        @click="selectTab(tab.hash);"
      >
        <span> {{ tab.name }} </span>
      </li>
    </ul>
    <div class="content"><slot></slot></div>
  </div>
</template>

<script>
export default {
  props: ["title"],
  data: () => {
    return {
      tabs: []
    };
  },
  computed: {
    actualTabs() {
      if (this.tabs.length > 0) return this.tabs.filter(tab => tab.amTab);
      return [];
    }
  },
  created() {
    this.tabs = this.$children;
  },
  mounted() {
    if (this.tabs.length > 0) this.tabs[0].active = true;
  },
  methods: {
    selectTab(hash) {
      this.tabs.forEach(tab => (tab.active = tab.hash === hash));
    }
  }
};
</script>

<style lang="scss" scoped>
$border: #efefef;
.page {
  h1 {
    font-size: 18px;
    margin: 0 0 10px 0;
    border-bottom: solid 1px $border;
    padding-bottom: 7px;
  }
  .tabs {
    position: relative;
    bottom: -1px;
    list-style: none;
    li {
      float: left;
      padding: 10px 20px;
      border: solid 1px $border;
      background: #fafafa;
      cursor: pointer;
      &.is-active {
        border-bottom: solid 1px white;
        background: white;
        cursor: default;
      }
    }
  }
  .content {
    clear: both;
    border: solid 1px $border;
    padding: 10px;
  }
}
</style>
