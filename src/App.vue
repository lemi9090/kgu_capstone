<template>
  <div class="viewport">
    <div class="content-box">
      <!-- Navigation Bar -->
      <header class="top-bar">
        <div class="left-group">
          <span class="logo">Business Pointer</span>
          <nav class="menu">
            <a class="menu-item" href="#">Dashboard</a>
            <a class="menu-item" href="#">Projects</a>
            <a class="menu-item" href="#">Meeting Logs</a>
          </nav>
        </div>
        <div class="right-group">
          <span class="user-id">guest</span>
          <div class="avatar"></div>
          <button class="hamburger" aria-label="menu">☰</button>
        </div>
      </header>       

      <!-- Greeting section -->
      <section class="greeting">
        <h1>Hello, Stranger!</h1>
        <p>Here's an overview of your current projects.</p>
      </section>

      <!-- 타일 영역: 행 단위로 분리 -->
      <div class="tiles-wrapper">
        <!-- 1행 -->
        <div class="tiles-row row1">
          <TotalProjects class="tile" />
          <TilePlaceholder class="tile" />
          <TilePlaceholder class="tile" />
        </div>

        <!-- 2행 -->
        <div class="tiles-row row2">
          <TilePlaceholder class="tile" />
          <TilePlaceholder class="tile" />
          <TilePlaceholder class="tile wide" />
        </div>

        <!-- 3행 -->
        <div class="tiles-row row3">
          <TilePlaceholder class="tile" />
          <TilePlaceholder class="tile" />
          <TilePlaceholder class="tile" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TotalProjects from './components/tiles/TotalProjects.vue'
import TilePlaceholder from './components/tiles/TilePlaceholder.vue'
export default { name: 'App', components: {
  TilePlaceholder,
  TotalProjects 
} }
</script>

<style scoped>
/* ① 화면 중앙에 박스를 두기 위한 래퍼 */
.viewport {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* ② 고정 크기의 흰색 캔버스 */
.content-box {
  aspect-ratio: 1.618 / 1;
  width: min(100%, calc((100vh - 20px) * 1.618));
  max-width: 1500px;

  background: #fff;
  border-radius: 16px;
  box-shadow: 0 6px 24px rgba(0, 0, 0, 0.08);
  padding: 40px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;

  /* height는 자동 계산 (aspect-ratio 기준) */
  overflow: hidden;
}
.top-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: nowrap;
  height: 56px;
  border-bottom: 1px solid #e5e7eb;
  margin-bottom: 16px;
}
/* 로고 전용 스타일 */
.logo{
  font-family:'Poppins',sans-serif;/* 원하는 글꼴 */
  font-size:18px;                  /* 작게 조정 */
  font-weight:700;
  white-space:nowrap;
}
/* 왼쪽·오른쪽 그룹 내부 배치 */
.left-group{display:flex;align-items:center;gap:24px;}
.menu{display:flex;gap:20px;}
.menu-item{font-size:15px;color:#374151;text-decoration:none;white-space:nowrap;}

.right-group{display:flex;align-items:center;gap:16px;margin-left:auto;}
.user-id{font-size:15px;font-weight:500;color:#111827;white-space:nowrap;}
.avatar{width:32px;height:32px;border-radius:50%;background:#d1d5db;}
.hamburger{background:none;border:none;font-size:22px;cursor:pointer;color:#374151;}

.tiles-wrapper {
  display: flex;
  flex-direction: column;
  gap: 24px;
  flex-grow: 1;
  justify-content: flex-start;
  height: 100%;
}

.tiles-row {
  display: grid;
  column-gap: 24px;
  row-gap: 24px;
  flex: 0 1 auto;
}

.row1 {
  grid-template-columns: repeat(3, 1fr);
  height: 20%;
}

.row2 {
  grid-template-columns: 1fr 1fr 1.25fr;
  height: 20%;
}

.row3 {
  grid-template-columns: repeat(3, 1fr);
  height: 50%;
}

.tile {
  width: 100%;
  height: 100%;
  display: flex;              /* ✅ 중요 */
  align-items: center;
  justify-content: center;
}

</style>

