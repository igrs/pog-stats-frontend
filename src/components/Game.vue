<template>
</template>

<script>
export default {
  data() {
    return {
      game: {
        title: 'POG 2016-201７ ADC vs IGRS',
        prize: '勝者に対し敗者は何かごちそうする。',
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
              },
            ],
          },
        ],
      },
    };
  },
}
</script>

<style lang="scss">
</style>
