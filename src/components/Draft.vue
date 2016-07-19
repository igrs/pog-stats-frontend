<template>
  <table class="table">
    <thead>
      <tr>
        <th>順位</th>
        <th>馬名</th>
        <th>戦績</th>
        <th>獲得賞金</th>
        <th>その他</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="horse in horses" v-bind:class="['c-white', horse.sex == '牡' ? 'bg-black' : 'bg-blue']">
        <td>{{ horse.ranking }}</td>
        <td>{{ horse.name }}</td>
        <td>{{ horse.record }}</td>
        <td>{{ horse.gotPrize }}万円</td>
        <td>性別: {{ horse.sex }}
          <br />厩舎: {{ horse.stable }}
          <br />生産: {{ horse.breeder }}
          <br />父馬: {{ horse.sire }}
          <br />母馬: {{ horse.dam }}
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: ['horses'],
};
</script>

<style>
</style>
