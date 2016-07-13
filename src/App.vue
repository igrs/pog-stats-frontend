<template>
  <section id="app" class="section">
    <section class="container grid-960">
      <menu></menu>
    </section>
  </section>
</template>

<script>
import Hello from './components/Hello';
import Menu from './components/Menu';

export default {
  components: {
    Hello,
    Menu,
  },
};
</script>

<style lang="scss">
@import '../node_modules/spectre.css/dist/spectre.min.css';
@import './css/common';

html {
  height: 100%;
  background: $base-c-gray;
}

section {
  &.section {
    background: $base-c-gray;
  }
}

.c-gray {
  color: $base-c-gray;
}

.c-yellow {
  color: $base-c-yellow;
}

.c-white {
  color: $base-c-white;
}

.c-black {
  color: $base-c-black;
}

.c-blue {
  color: $base-c-gray;
}

.material-icons {
  vertical-align: middle;

  &.md-12 {
    font-size: 12px;
  }
  &.md-18 {
    font-size: 18px;
  }
  &.md-24 {
    font-size: 24px;
  }
  &.md-36 {
    font-size: 36px;
  }
  &.md-48 {
    font-size: 48px;
  }
}
</style>
