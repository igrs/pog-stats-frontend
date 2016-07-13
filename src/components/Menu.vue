<template>
  <section class="notes text-center">
    <ul class="tab inline-flex">
      <li v-for="item in items"
          class="tab-item"
          v-bind:class="{ 'active': item.current }"
          @click="clickMenu($index)">
        <a href="#elements">{{ item.name }}</a>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { name: 'Summary', current: true },
        { name: 'Games', current: false },
        { name: 'Profile', current: false },
        { name: 'Etc', current: false },
      ],
    };
  },
  methods: {
    clickMenu(index) {
      const item = this.items[index];
      if (!item.current) {
        for (let i = 0; i < this.items.length; i++) {
          this.items[i].current = false;
        }
        this.items[index].current = true;
      }
    },
  },
};
</script>

<style lang="scss">
@import '../css/common';
.tab {
  .tab-item {
    &.active a {
      border-bottom-color: $base-c-yellow;
      color: $base-c-yellow;
      &:hover,:focus {
        border-bottom-color: $base-c-yellow;
        color: $base-c-yellow;
      }
    }
    & a {
      border-bottom-color: $base-c-white;
      color: $base-c-white;
      &:hover,:focus {
        border-bottom-color: $base-c-lite-gray;
        color: $base-c-lite-gray;
      }
    }
  }
}
</style>
