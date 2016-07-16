<template>
  <section id="app" class="section">
    <section class="container grid-960">
      <menu></menu>
      <game></game>
    </section>
  </section>
</template>

<script>
import Menu from './components/Menu';
import Game from './components/Game';

export default {
  components: {
    Menu,
    Game,
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

.bg-gray {
  background: $base-c-gray;
  border-color: $base-c-gray;
}

.c-yellow {
  color: $base-c-yellow;
}
.bg-yellow {
  background: $base-c-yellow;
  border-color: $base-c-yellow;
}

.c-white {
  color: $base-c-white;
}
.bg-white {
  background: $base-c-white;
  border-color: $base-c-white;
}

.c-black {
  color: $base-c-black;
}
.bg-black {
  background: $base-c-black;
  border-color: $base-c-black;
}

.c-blue {
  color: $base-c-gray;
}
.bg-blue {
  background: $base-c-blue;
  border-color: $base-c-blue;
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
