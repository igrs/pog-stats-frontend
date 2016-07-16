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
  <div class="columns">
    <div class="column col-6" v-for="user in users">
      <div class="card">
        <div class="card-header">
          <h4 class="card-title">{{ user.name | uppercase }}</h4>
          <h6 class="card-meta text-right">{{ user.total }}万円</h6>
        </div>
        <div class="divider"></div>
        <div class="card-body">
          <table class="table table-hover">
            <thead>
              <tr>
                <th>馬名</th>
                <th>戦績</th>
                <th>獲得賞金</th>
                <th>その他</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="horse in user.horses">
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
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'POG 2016-201７ ADC vs IGRS',
      prize: '勝者に対し敗者は何か美味しいものをごちそうする。',
      period: '2016年ダービー翌週の新馬戦から2017年日本ダービー終了まで。',
      regulation: '指名頭数10頭\n牡牝の数に制限なし\n指名馬の総獲得賞金を競う。',
      updated_at: '2016/05/01',
      users: [
        {
          name: 'adc',
          total: 0,
          horses: [
            {
              ranking: 1,
              name: 'トゥザクラウン',
              sire: 'キングカメハメハ',
              dam: 'トゥザヴィクトリー',
              sex: '牡',
              record: '0-0-0-0',
              stable: '（栗）池江',
              breeder: 'ノーザンファーム',
              gotPrize: 0,
            },
          ],
        },
        {
          name: 'igrs',
          total: 0,
          horses: [
            {
              ranking: 1,
              name: 'ラボーナ',
              sire: 'ルーラーシップ',
              dam: 'ハッピーパス',
              sex: '牡',
              record: '0-0-0-0',
              stable: '（美）藤沢',
              breeder: 'ノーザンファーム',
              gotPrize: 0,
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss">
</style>
