<template>
  <h1 class="text-center c-white">{{ title }}</h1>
  <div class="columns">
    <div class="column col-4">
      <div class="card">
        <div class="card-header">
          <h4 class="card-title">報酬</h4>
          <h6 class="card-meta">prize</h6>
        </div>
        <div class="divider"></div>
        <div class="card-body">{{ prize }}</div>
      </div>
    </div>
    <div class="column col-4">
      <div class="card">
        <div class="card-header">
          <h4 class="card-title">期間</h4>
          <h6 class="card-meta">period</h6>
        </div>
        <div class="divider"></div>
        <div class="card-body">{{ period }}</div>
      </div>
    </div>
    <div class="column col-4">
      <div class="card">
        <div class="card-header">
          <h4 class="card-title">規定</h4>
          <h6 class="card-meta">regulation</h6>
        </div>
        <div class="divider"></div>
        <div class="card-body">{{ regulation }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['title', 'prize', 'period', 'regulation'],
};
</script>
