<template>
  <div class="kh-content">
    <div class="kh-content-extend">
      <div class="kh-row">
        <div class="ku-item">
          <div class="kh-label">已合作园区</div>
          <div class="kh-value">549</div>
        </div>
        <div class="ku-item">
          <div class="kh-label">意向合作园区</div>
          <div class="kh-value">580</div>
        </div>
      </div>

      <div class="kh-row">
        <div class="ku-item">
          <div class="kh-label">已合作商场</div>
          <div class="kh-value">208</div>
        </div>
        <div class="ku-item">
          <div class="kh-label">意向合作商场</div>
          <div class="kh-value">1200</div>
        </div>
      </div>

      <div class="kh-row">
        <div class="ku-item">
          <div class="kh-label">已合作小区</div>
          <div class="kh-value">720</div>
        </div>
        <div class="ku-item">
          <div class="kh-label">意向合作学校</div>
          <div class="kh-value">1992</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.kh-row {
  display: flex;
  justify-content: center;
  line-height: 40px;
  width: 500px;
  margin-bottom: 30px;
}

.kh-content {
  padding: 20px 30px;
  color: #56a2fd;

  .kh-content-extend {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}

.ku-item {
  display: flex;
  width: 90%;

  .kh-label {
    margin-right: 20px;
  }

  .kh-value {
    font-weight: bold;
    font-size: 26px;
  }
}
</style>
<script setup lang="ts">
</script>