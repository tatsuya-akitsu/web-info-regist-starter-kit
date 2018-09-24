<template>
  <section class="md-section">
    <div class="md-wrapper">
      <el-steps :active="3" align-center>
        <el-step title="Step 1"></el-step>
        <el-step title="Step 2"></el-step>
        <el-step title="Step 3"></el-step>
        <el-step title="Step 4"></el-step>
      </el-steps>
      <form id="configform" class="md-form" name="configform" method="post">
        <div class="md-form-item fle-r">
          <label>サーバー名</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              placeholder="さくらレンタルサーバー"
              v-model="$store.state.serverCompanyName"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>サーバーパスワード</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.serverPassword"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>サーバー管理画面ログインID</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.serverAdminLoginId"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>サーバー管理画面ログインパスワード</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.serverAdminPassword"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>FTPサーバー名</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.ftpServerName"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>FTPアカウント名</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.ftpServerAccount"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>WordPressログインID</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.wpLoginId"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>WordPressログインパスワード</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.wpLoginPassword"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>その他アクセス制限ID</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.otherLoginId"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <div class="md-form-item fle-r">
          <label>その他アクセス制限パスワード</label>
          <div class="md-form-box">
            <el-input
              name="clientName"
              v-model="$store.state.otherLoginPassword"
              class="md-form-control"
            ></el-input>
          </div>
        </div>
        <el-button class="md-btn--style02" @click="$router.push('/production')">戻る</el-button>
        <el-button class="md-btn--style01" @click="$router.push('/confirm')">確認</el-button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: 'production',
}
</script>
