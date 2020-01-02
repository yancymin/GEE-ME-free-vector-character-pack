<template>
  <div class="card">
    <img :src="svgSrc" alt srcset />
    <div class="buttons">
      <a :href="svgSrc" download>SVG</a>
      <a :href="pngSrc" download>PNG</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'card',
  props: ['svgSrc', 'pngSrc'],
};
</script>

<style lang="scss" scoped>
@import '../style/global.scss';

.card {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  background: #edf1f7;
  border-radius: 12px;
  transition: all 0.2s ease;
  overflow: hidden;
  box-shadow: inset 0 0 0 4px transparent;

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

  .buttons {
    display: flex;
    justify-content: space-between;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    opacity: 0;
    transform: translateY(100%);
    transition: all 0.25s ease;

    a {
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 50%;
      height: 40px;
      color: white;
      background: #333;
      transition: all 0.25s ease;
      @include font(13, 600, 13, 0) {
        color: white;
      }

      &:nth-of-type(1) {
        border-radius: 0 0 0 12px;

        &:hover {
          & ~ a {
            &::after {
              opacity: 0;
            }
          }
        }
      }
      &:nth-of-type(2) {
        position: relative;
        border-radius: 0 0 12px 0;

        &::after {
          content: '';
          position: absolute;
          left: -1px;
          display: block;
          height: 55%;
          width: 1px;
          background-color: rgb(92, 92, 92);
          transition: all 0.25s ease;
        }
      }

      &:hover {
        text-decoration: underline;
        background: rgb(10, 10, 10);

        &:nth-of-type(2) {
          &::after {
            opacity: 0;
          }
        }
      }
    }
  }

  &:hover {
    box-shadow: inset 0 0 0 4px #333;

    .buttons {
      opacity: 1;

      transform: translateY(0);
    }
  }
}
</style>
