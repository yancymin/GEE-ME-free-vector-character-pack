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
  /* padding: 10px; */

  img {
    /* width: 100%;
    max-width: 53%; */
    max-height: 90%;
  }
}
</style>
