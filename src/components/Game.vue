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
              <tr v-for="horse in user.horses" v-bind:class="['c-white', horse.sex == '牡' ? 'bg-black' : 'bg-blue']">
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
              stable: '池江（栗）',
              gotPrize: 0,
              breeder: 'ノーザンファーム',
            },
            {
              ranking: 2,
              name: 'アルアイン',
              sire: 'ディープインパクト',
              dam: 'ドバイマジェスティ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '池江(栗)',
              breeder: 'ノーザンファーム',
            },
            {
              ranking: 3,
              name: 'グローブシアター',
              sire: 'キングカメハメハ',
              dam: 'シーザリオ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '角居(栗)',
              breeder: 'ノーザンファーム',
            },
            {
              ranking: 4,
              name: 'フローレスマジック',
              sire: 'ディープインパクト',
              dam: 'マジックストーム',
              sex: '牝',
              record: '0-0-0-0',
              stable: '木村(美)',
              breeder: 'ノーザンファーム',
            },
            {
              ranking: 5,
              name: 'モクレレ',
              sire: 'ディープインパクト',
              dam: 'アパパネ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '国枝(美)',
              breeder: 'ノーザンファーム',
            },
            {
              ranking: 6,
              name: 'サトノアーサー',
              sire: 'ディープインパクト',
              dam: 'キングスローズ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '池江(栗)',
              breeder: 'ノーザンファーム',
            },
            {
              ranking: 7,
              name: 'ワンフォーオール',
              sire: 'ディープインパクト',
              dam: 'ラヴェリータ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '松元(栗)',
              breeder: 'ノースヒルズ',
            },
            {
              ranking: 7,
              name: 'コロナシオン',
              sire: 'キングカメハメハ',
              dam: 'ブエナビスタ',
              sex: '牝',
              record: '0-0-0-0',
              stable: '池添(栗)',
              breeder: 'ノーザンファーム',
            },
            {
              ranking: 9,
              name: 'グランデセーヌ',
              sire: 'ゼンノロブロイ',
              dam: 'リッチダンサー',
              sex: '牝',
              record: '0-0-0-0',
              stable: '藤沢(美)',
              breeder: 'ノーザンファーム',
            },
            {
              ranking: 10,
              name: 'ポポカテペトル',
              sire: 'ディープインパクト',
              dam: 'ミスパスカリ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '友道(栗)',
              breeder: 'ノーザンファーム',
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
              stable: '藤沢（美）',
              breeder: 'ノーザンファーム',
              gotPrize: 0,
            },
            {
              ranking: 2,
              name: 'ムーヴザワールド',
              sire: 'ディープインパクト',
              dam: 'リッスン',
              sex: '牡',
              record: '0-0-0-0',
              stable: '石坂（栗）',
              breeder: 'ノーザンファーム',
              gotPrize: 0,
            },
            {
              ranking: 3,
              name: 'スワーヴリチャード',
              sire: 'ハーツクライ',
              dam: 'ピラミマ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '庄野（栗）',
              breeder: 'ノーザンファーム',
              gotPrize: 0,
            },
            {
              ranking: 4,
              name: 'レイデオロ',
              sire: '父：キングカメハメハ',
              dam: '母：ラドラーダ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '藤沢（美）',
              breeder: 'ノーザンファーム',
              gotPrize: 0,
            },
            {
              ranking: 5,
              name: 'ゼンノワスレガタミ',
              sire: '父：キングカメハメハ',
              dam: 'ダイヤモンドビコー',
              sex: '牡',
              record: '0-0-0-0',
              stable: '中内田（栗）',
              breeder: '村上欽哉',
              gotPrize: 0,
            },
            {
              ranking: 6,
              name: 'ディーパワンサ',
              sire: 'ディープブリランテ',
              dam: 'ポロンナルワ',
              sex: '牝',
              record: '1-0-0-0',
              stable: '松下（栗）',
              breeder: 'ノーザンファーム',
              gotPrize: 700.0,
            },
            {
              ranking: 7,
              name: 'クライベイビー',
              sire: 'ハーツクライ',
              dam: 'スカイアライアンス',
              sex: '牝',
              record: '0-0-0-0',
              stable: '須貝（栗）',
              breeder: '白老ファーム',
              gotPrize: 0,
            },
            {
              ranking: 8,
              name: 'アンデスクイーン',
              sire: '父：タートルボウル',
              dam: '母：レイナカスターニャ',
              sex: '牝',
              record: '0-0-0-0',
              stable: '西園（栗）',
              breeder: 'ノーザンファーム',
              gotPrize: 0,
            },
            {
              ranking: 9,
              name: 'イストワールファム',
              sire: 'ローエングリン',
              dam: 'ヒストリックレディ',
              sex: '牝',
              record: '0-0-0-0',
              stable: '古賀（美）',
              breeder: 'ノーザンファーム',
              gotPrize: 0,
            },
            {
              ranking: 10,
              name: 'クライムメジャー',
              sire: 'ダイワメジャー',
              dam: 'クライウィズジョイ',
              sex: '牡',
              record: '0-0-0-0',
              stable: '池江（栗）',
              breeder: 'レイクヴィラファーム',
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
