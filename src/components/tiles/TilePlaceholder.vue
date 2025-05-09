<!-- components/tiles/TilePlaceholder.vue -->
<template>
  <div class="tile">
    <slot>Tile</slot>
  </div>
</template>

<script>
export default { name: 'TilePlaceholder' }
</script>

<style>
.tile {
  background: #fff;
  border: 1px solid #cbd5e1;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #64748b;
  font-weight: 600;
  width: 100%;
  height: 100%;
}

</style>
