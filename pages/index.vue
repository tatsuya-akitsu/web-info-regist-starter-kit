<template>
  <section class="md-section">
    <div class="md-wrapper">
      <el-steps :active="1" align-center>
        <el-step title="Step 1"></el-step>
        <el-step title="Step 2"></el-step>
        <el-step title="Step 3"></el-step>
        <el-step title="Step 4"></el-step>
      </el-steps>
      <form id="requestform" class="md-form" name="requestform" method="post">
        <div class="md-form-item fle-r">
          <label>クライアント名</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              placeholder="株式会社○○様"
              v-model="$store.state.clientName"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>納品希望日</label>
          <div class="md-form-box">
            <el-date-picker
              v-model="$store.state.deliveryDate"
              type="date"
              placeholder="納品希望日を選択してください">
            </el-date-picker>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>サイト名</label>
          <div class="md-form-box">
            <el-input
              name="siteName"
              v-model="$store.state.siteName"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>サイトディスクリプション</label>
          <div class="md-form-box">
            <el-input
              name="siteDescription"
              placeholder="このサイトは、お客様に弊社の情報をお届けするためのサイトです。"
              v-model="$store.state.siteDescription"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>OGPテキスト</label>
          <div class="md-form-box">
            <el-input
              name="ogpDescription"
              placeholder="このサイトは、お客様に弊社の情報をお届けするためのサイトです。"
              v-model="$store.state.ogpDescription"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>制作目的</label>
          <div class="md-form-box">
            <el-checkbox-group v-model="$store.state.checkList">
              <el-checkbox label="広告用LP"></el-checkbox>
              <el-checkbox label="サイトリニューアル"></el-checkbox>
              <el-checkbox label="新規制作"></el-checkbox>
              <el-checkbox label="既存サイト見栄え修正"></el-checkbox>
              <el-checkbox label="既存サイト機能修正"></el-checkbox>
              <el-checkbox label="その他"></el-checkbox>
            </el-checkbox-group>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>ターゲット層</label>
          <div class="md-form-box">
            <div class="md-form-box--second">
              <h3 class="md-ttl md-ttl--label">年齢層</h3>
              <div class="md-form-box--inner">
                <el-slider
                  v-model="$store.state.generation"
                  range
                  show-stops
                  :step="10"
                  :max="60"
                ></el-slider>
              </div>
            </div>
            <div class="md-form-box--second">
              <h3 class="md-ttl md-ttl--label">性別</h3>
              <div class="md-form-box--inner">
                <el-radio v-model="$store.state.gender" label="男性" border>男性</el-radio>
                <el-radio v-model="$store.state.gender" label="女性" border>女性</el-radio>
              </div>
            </div>
            <div class="md-form-box--second">
              <h3 class="md-ttl md-ttl--label">職業</h3>
              <div class="md-form-box--inner">
                <el-radio v-model="$store.state.employment" label="会社員" border>会社員</el-radio>
                <el-radio v-model="$store.state.employment" label="学生" border>学生</el-radio>
                <el-radio v-model="$store.state.employment" label="フリーター" border>フリーター</el-radio>
                <el-radio v-model="$store.state.employment" label="主婦" border>主婦</el-radio>
              </div>
            </div>
            <div class="md-form-box--second">
              <h3 class="md-ttl md-ttl--label">地方圏</h3>
              <div class="md-form-box--inner">
                <el-radio v-model="$store.state.local" label="都内" border>都内</el-radio>
                <el-radio v-model="$store.state.local" label="地方" border>地方</el-radio>
              </div>
            </div>
          </div>
        </div>
        <el-button class="md-btn--style01" @click="$router.push('/production')">次へ</el-button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: "main"
};
</script>
