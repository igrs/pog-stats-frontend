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
      <tr v-for="horse in horses"
          class="horse"
          v-bind:class="['c-white', horse.sex == '牡' ? 'bg-black' : 'bg-blue']"
          @click="showDraftModifyModal($index)">
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
  <draft-modify-modal :show.sync="showModal" :horse.sync="target">
  </draft-modif-modal>
</template>

<script>
import DraftModifyModal from './DraftModifyModal';
export default {
  components: {
    DraftModifyModal,
  },
  data() {
    return {
      target: {
        id: null,
        ranking: null,
        name: '',
        record: '',
        gotPrize: 0,
        sex: '',
        stable: '',
        breeder: '',
        sire: '',
        dam: '',
      },
      showModal: false,
    };
  },
  props: ['horses'],
  methods: {
    showDraftModifyModal(index) {
      Object.assign(this.target, this.horses[index]);
      this.showModal = true;
    },
  },
};
</script>

<style lang="scss">
.horse {
  cursor: pointer;
}
</style>
