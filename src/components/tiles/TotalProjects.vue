<template>
  <div class="tile-box">
    <h2 class="tile-title">Total Projects</h2>
    <p class="tile-value">3</p>
  </div>
</template>

<script>
export default {
  name: 'TotalProjects'
}
</script>

<style scoped>
.tile-box {
  background: #f9fafb;
  border-radius: 12px;
  padding: 20px;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  box-shadow: 0 2px 6px rgba(0,0,0,0.05);
}

.tile-title {
  font-size: 16px;
  font-weight: 600;
  color: #111827;
  margin-bottom: 8px;
}

.tile-value {
  font-size: 28px;
  font-weight: bold;
  color: #111827;
}
</style>
