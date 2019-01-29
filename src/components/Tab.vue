<template>
  <div class="tab-content" v-if="active"><slot></slot></div>
</template>

<script>
export default {
  props: {
    name: {
      required: true
    }
  },
  data: () => {
    return {
      active: false,
      amTab: true
    };
  },
  methods: {
    computedId() {
      return this.name.toLowerCase().replace(/ /g, "-");
    },
    hash() {
      return "#" + this.computedId;
    }
  }
};
</script>
