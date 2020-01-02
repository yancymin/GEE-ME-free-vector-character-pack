<template>
  <div class="card">
    <img :src="svgSrc" alt srcset />
  </div>
</template>

<script>
export default {
  name: 'card',
  props: ['svgSrc'],
};
</script>

<style lang="scss" scoped>
.card {
  display: flex;
  justify-content: center;
  align-items: center;
  /* min-width: 200px;
  max-width: 300px; */
  height: 100%;
  background: #edf1f7;
  border-radius: 12px;

  img {
    max-height: 90%;
    opacity: 0;
    animation: svgShow 0.4s ease forwards;

    @keyframes svgShow {
      to {
        opacity: 1;
      }
    }
  }
}
</style>
