<template>
  <div class="progress-wrapper">
    <div
      class="progress-item"
      v-for="(progress, index) in progresses"
      :class="{
        'passed': progress.isPassed,
        'active': progress.name === isActive.name,
        'last': progress.name === isLast.name
        }"
      :key="index"
      @click="changeTab(progress)"
    >{{progress.name}}</div>
  </div>
</template>

<script>
export default {
  props: {
    progresses: Array,
    isActive: Object,
    isLast: Object
  },
  methods: {
    changeTab(progress) {
      if (progress.isPassed) this.$emit("switch-tab", progress.name);
    }
  }
};
</script>

<style lang="scss">
.progress-wrapper {
  display: flex;
}
.progress-item {
  color: #c1cad8;
  font-size: 1rem;
  padding: 0.5rem 1rem;
  border: none;
}
.passed {
  background-color: #ecf2fe;
  &:first-child {
    border-top-left-radius: 0.4rem;
    border-bottom-left-radius: 0.4rem;
  }
}
.active {
  color: #0e1952;
}
.last {
  border-top-right-radius: 1rem;
  border-bottom-right-radius: 1rem;
}
</style>