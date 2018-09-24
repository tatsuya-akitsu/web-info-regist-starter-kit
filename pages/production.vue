<template>
  <section class="md-section">
    <div class="md-wrapper">
      <el-steps :active="2" align-center>
        <el-step title="Step 1"></el-step>
        <el-step title="Step 2"></el-step>
        <el-step title="Step 3"></el-step>
        <el-step title="Step 4"></el-step>
      </el-steps>
      <form id="productionform" class="md-form" name="productionform" method="post">
        <div class="md-form-item fle-r">
          <label>使用プラットフォーム</label>
          <div class="md-form-box">
            <el-radio v-model="$store.state.webPlatform" label="静的サイト" border>静的サイト</el-radio>
            <el-radio v-model="$store.state.webPlatform" label="WordPress" border>WordPress</el-radio>
            <el-radio v-model="$store.state.webPlatform" label="Strikingly" border>Strikingly</el-radio>
            <el-radio v-model="$store.state.webPlatform" label="WiX" border>WiX</el-radio>
            <el-radio v-model="$store.state.webPlatform" label="独自CMS" border>独自CMS</el-radio>
            <el-radio v-model="$store.state.webPlatform" label="その他CMS" border>その他CMS</el-radio>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>表示プラットフォーム</label>
          <div class="md-form-box">
            <el-checkbox :indeterminate="$store.state.isPlatIndeterminate" v-model="$store.state.checkDisplayPlatAll" @change="handlecheckDisplayPlatAllChange">すべて選択</el-checkbox>
            <el-checkbox-group v-model="$store.state.checkedDisplayPlatform" @change="handleCheckedDisplayPlat">
              <el-checkbox v-for="plat in displayPlat" :label="plat" :key="plat">{{plat.val}}</el-checkbox>
            </el-checkbox-group>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>レスポンシブ対応範囲</label>
          <div class="md-form-box">
            <el-checkbox :indeterminate="$store.state.isScopeIndeterminate" v-model="$store.state.checkSupportedScopeAll" @change="handlecheckSupportedScopeAllChange">すべて選択</el-checkbox>
            <el-checkbox-group v-model="$store.state.checkedSupportedScope" @change="handleCheckedSupportedScope">
              <el-checkbox v-for="scope in supportedScope" :label="scope" :key="scope">{{scope.val}}</el-checkbox>
            </el-checkbox-group>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>サイトイメージURL</label>
          <div class="md-form-box">
            <el-input
              name="referenceSite1"
              placeholder="google.com"
              v-model="$store.state.referenceSite1"
              class="md-form-control"
            >
              <template slot="prepend">http://</template>
            </el-input>
            <el-input
              name="referenceSite2"
              placeholder="yahoo.co.jp"
              v-model="$store.state.referenceSite2"
              class="md-form-control"
              >
              <template slot="prepend">http://</template>
            </el-input>
            <el-input
              name="referenceSite3"
              placeholder="bing.com"
              v-model="$store.state.referenceSite3"
              class="md-form-control"
            >
              <template slot="prepend">http://</template>
            </el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>その他サイトイメージ（パーツ単位）</label>
          <div class="md-form-box">
            <el-input
              type="textarea"
              :rows="5"
              placeholder="http://○○.comのお問い合わせフォームはそのまま使用したい"
              v-model="$store.state.otherSiteImage"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>必要機能（機能と詳細）</label>
          <div class="md-form-box">
            <el-input
              type="textarea"
              :rows="5"
              placeholder="資料請求用と求人用の2種のフォームを設置したい"
              v-model="$store.state.necessaryFunctional"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>画像</label>
          <div class="md-form-box">
            <el-radio v-model="$store.state.images" label="新規作成" border>新規作成</el-radio>
            <el-radio v-model="$store.state.images" label="クライアントが用意" border>クライアントが用意</el-radio>
            <el-radio v-model="$store.state.images" label="既存サイトから回収" border>既存サイトから回収</el-radio>
          </div>
        </div>
        <div class="md-form-item fle-r" v-if="$store.state.images === '既存サイトから回収' ">
          <label>回収サイトURL</label>
          <div class="md-form-box">
            <el-input
              name="referenceSite1"
              placeholder="google.com"
              v-model="$store.state.collectionImageUrl"
              class="md-form-control"
            >
              <template slot="prepend">http://</template>
            </el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>テキスト</label>
          <div class="md-form-box">
            <el-radio v-model="$store.state.texts" label="新規作成" border>新規作成</el-radio>
            <el-radio v-model="$store.state.texts" label="クライアントが用意" border>クライアントが用意</el-radio>
            <el-radio v-model="$store.state.texts" label="既存サイトから回収" border>既存サイトから回収</el-radio>
          </div>
        </div>
        <div class="md-form-item fle-r" v-if="$store.state.texts === '既存サイトから回収' ">
          <label>回収サイトURL</label>
          <div class="md-form-box">
            <el-input
              name="referenceSite1"
              placeholder="google.com"
              v-model="$store.state.collectionTextUrl"
              class="md-form-control"
            >
              <template slot="prepend">http://</template>
            </el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>コピーライト</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              placeholder="©sample.com"
              v-model="$store.state.copyright"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <el-button class="md-btn--style02" @click="$router.push('/')">戻る</el-button>
        <el-button class="md-btn--style01" @click="$router.push('/config')">次へ</el-button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: 'production',
  data: () => {
    return {
      displayPlat: [],
      supportedScope: [],
    }
  },
  created () {
    console.log(this.$store.state)
    this.displayPlat = this.$store.state.displayPlatform
    this.supportedScope = this.$store.state.supportedScope
  },
  methods: {
    handlecheckDisplayPlatAllChange(val) {
      this.$store.state.checkedDisplayPlatform = val ? this.displayPlat : [];
      this.$store.state.isPlatIndeterminate = false;
    },
    handleCheckedDisplayPlat(value) {
      let checkedCount = value.length;
      this.$store.state.checkDisplayPlatAll = checkedCount === this.displayPlat.length;
      this.$store.state.isPlatIndeterminate = checkedCount > 0 && checkedCount < this.displayPlat.length;
    },
    handlecheckSupportedScopeAllChange(val) {
      this.$store.state.checkedSupportedScope = val ? this.supportedScope : [];
      this.$store.state.isScopeIndeterminate = false;
    },
    handleCheckedSupportedScope(value) {
      let checkedCount = value.length;
      this.$store.state.checkSupportedScopeAll = checkedCount === this.supportedScope.length;
      this.$store.state.isScopeIndeterminate = checkedCount > 0 && checkedCount < this.supportedScope.length;
    },
  }
}
</script>
