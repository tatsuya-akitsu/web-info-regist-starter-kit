<template>
  <section class="md-section">
    <div class="md-wrapper">
      <el-steps :active="4" align-center>
        <el-step title="Step 1"></el-step>
        <el-step title="Step 2"></el-step>
        <el-step title="Step 3"></el-step>
        <el-step title="Step 4"></el-step>
      </el-steps>
      <div class="confirm-wrap">
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">クライアント名</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.clientName }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">納品希望日</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ date }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">サイト名</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.siteName }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">サイトディスクリプション</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.siteDescription }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">OGPテキスト</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.ogpDescription }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">制作目的</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item" v-for="item in $store.state.checkList" :key="item">{{ item }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">年齢層</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">
              {{ $store.state.generation[0] }}代〜
              {{ $store.state.generation[1] }}代
            </p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">性別</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.gender }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">職業</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.employment }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">地方圏</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.local }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">使用プラットフォーム</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">
              {{ $store.state.webPlatform }}
            </p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">表示プラットフォーム</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item md-plt" v-for="item in $store.state.checkedDisplayPlatform" :key="item">
              {{ item.val }}
            </p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">レスポンシブ対応</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item md-scope" v-for="item in $store.state.checkedSupportedScope" :key="item">
              {{ item.val }}
            </p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">サイトイメージURL</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">
              {{ $store.state.referenceSite1 }}<br />
              {{ $store.state.referenceSite2 }}<br />
              {{ $store.state.referenceSite3 }}
            </p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">その他サイトイメージ</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.otherSiteImage }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">必要機能</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.necessaryFunctional }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">画像</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.images }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">回収サイトURL</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.collectionImageUrl }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">テキスト</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.texts }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">回収サイトURL</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.collectionTextUrl }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">コピーライト</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.copyright }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">サーバー名</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.serverCompanyName }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">サーバーパスワード</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.serverPassword }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">サーバー管理画面ログインID</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.serverAdminLoginId }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">サーバー管理画面ログインパスワード</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.serverAdminPassword }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">FTPサーバー名</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.ftpServerName }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">FTPアカウント名</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.ftpServerAccount }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">WordPressログインID</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.wpLoginId }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">WordPressログインパスワード</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.wpLoginPassword }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">その他アクセス制限ID</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.otherLoginId }}</p>
          </div>
        </div>
        <div class="md-confirm-item">
          <p class="md-text md-text--confirm-label">その他アクセス制限パスワード</p>
          <div class="md-confirm-box">
            <p class="md-text md-text--confirm-item">{{ $store.state.otherLoginPassword }}</p>
          </div>
        </div>
        <el-button class="md-btn--style02" @click="$router.push('/config')">戻る</el-button>
        <a id="download" class="md-btn--style01 md-btn--download" href="#" @click="downloadCSV">ダウンロード</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'confirm',
  data: () => {
    return {
      date: '',
      pltList: [],
      scopeList: []
    }
  },
  created () {
    console.log(this.$store.state)
    let date = this.$store.state.deliveryDate
    const momentDate = this.$moment(date).format('YYYY/MM/DD')
    this.date = momentDate

    const platforms = this.$store.state.checkedDisplayPlatform
    for (let i = 0; i < platforms.length; i++) {
      this.pltList.push(platforms[i].val)
    }
    const scope = this.$store.state.checkedSupportedScope
    for (let i = 0; i < scope.length; i++) {
      this.scopeList.push(scope[i].val)
    }
  },
  methods: {
    downloadCSV() {
      // 配列 の用意
      let array_data = [
        ['クライアント名', this.$store.state.clientName],
        ['納品希望日', this.date],
        ['サイト名', this.$store.state.siteName],
        ['サイトディスクリプション', this.$store.state.siteDescription],
        ['OGPテキスト', this.$store.state.ogpDescription],
        ['制作目的', this.$store.state.checkList[0]],
        ['年齢層', this.$store.state.generation[0], this.$store.state.generation[1]],
        ['性別', this.$store.state.gender],
        ['職業', this.$store.state.employment],
        ['地方圏', this.$store.state.local],
        ['使用プラットフォーム', this.$store.state.webPlatform],
        ['表示プラットフォーム', this.pltList],
        ['レスポンシブ対応', this.scopeList],
        ['サイトイメージURL', this.$store.state.referenceSite1, this.$store.state.referenceSite2, this.$store.state.referenceSite3],
        ['その他サイトイメージ', this.$store.state.otherSiteImage],
        ['必要機能', this.$store.state.necessaryFunctional],
        ['画像', this.$store.state.images],
        ['画像回収URL', this.$store.state.collectionImageUrl],
        ['テキスト', this.$store.state.texts],
        ['テキスト回収URL', this.$store.state.collectionTextUrl],
        ['コピーライト', this.$store.state.copyright],
        ['サーバー名', this.$store.state.serverCompanyName],
        ['サーバーパスワード', this.$store.state.serverPassword],
        ['サーバー管理画面ログインID', this.$store.state.serverAdminLoginId],
        ['サーバー管理画面ログインパスワード', this.$store.state.serverAdminPassword],
        ['FTPサーバー名', this.$store.state.ftpServerName],
        ['FTPアカウント名', this.$store.state.ftpServerAccount],
        ['WordPressログインID', this.$store.state.wpLoginId],
        ['WordPressログインパスワード', this.$store.state.wpLoginPassword],
        ['その他アクセス制限ID', this.$store.state.otherLoginId],
        ['その他アクセス制限パスワード', this.$store.state.otherLoginPassword]
      ]
      // let array_data = [['りんご',1,200],['メロン',2,4000],['バナナ',4,500]];
      // BOM の用意（文字化け対策）
      const bom = new Uint8Array([0xEF, 0xBB, 0xBF]);
      // CSV データの用意
      const csv_data = array_data.map(function(l){return l.join(',')}).join('\r\n');
      const blob = new Blob([bom, csv_data], { type: 'text/csv' });
      const url = (window.URL || window.webkitURL).createObjectURL(blob);
      const a = document.getElementById('download');
      a.download = 'data.csv';
      a.href = url;
    }
  }
}
</script>
