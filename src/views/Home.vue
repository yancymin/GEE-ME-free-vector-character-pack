<template>
  <div class="home">
    <div class="side-panel">
      <div class="side-panel_top">
        <img class="logo" src="../assets/logo.svg" alt srcset />
        <!--eslint-disable -->
        <p>GEE! ME is a great set of flat graphics required, 100 cartoon characters and over 400 coolest objects. You can use it in any design or development projects. It’s completely free and just enjoy it~</p>
        <!--eslint-enable -->
        <a download href="/people/GEE-ME-Vector-Character-Pack.sketch">
          <img src="../assets/Sketch_Logo.svg" alt />
          Sketch
        </a>
        <a
          href="https://www.figma.com/file/ReHss0R5s19m52es6hlFPH/GEE-ME-Vector-Character-Pack?node-id=0%3A1"
          target="_blank"
        >
          <img src="../assets/Figma_Logo.svg" alt />
          Figma
        </a>
      </div>
      <div class="side-panel_bottom">
        <span>Designers</span>
        <div class="links">
          <a target="_blank" href="https://yorkun.com">Yorkun</a>
          <span>/</span>
          <a target="_blank" href="https://www.hwoma.com/">Hwoma</a>
          <span>/</span>
          <a target="_blank" href="https://yancymin.design">Yancy Min</a>
          <span>/</span>
          <a target="_blank" href="https://www.liuchangyi.com/">Charlie Liu</a>
        </div>
        <div class="social">
          <!--eslint-disable -->
          <a
            href="https://www.producthunt.com/posts/gee-me?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-gee-me"
            target="_blank"
          >
            <img
              src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=179779&theme=light"
              alt="GEE! ME - Free Vector Character Pack - 100 Characters Free Download | Product Hunt Embed"
              style="width: 250px; height: 54px;"
              width="250px"
              height="54px"
            />
          </a>
          <!--eslint-enable -->
          <a href="https://dribbble.com/geetest" target="_blank">
            <img src="../assets/dribbble.svg" alt />
          </a>
          <a href="https://github.com/yancymin/GEE-ME-free-vector-character-pack" target="_blank">
            <img src="../assets/github.svg" alt />
          </a>
        </div>
        <span>Made with ❤️ in Wuhan</span>
        <span>
          Copyright © 2020
          <a href="https://bookmark.geetest.design/" target="_blank">G-Design</a>
        </span>
      </div>
    </div>
    <div class="container">
      <Card v-for="(c,index) in svgs" :svgSrc="svgs[index]" :pngSrc="pngs[index]" :key="index" />
    </div>
  </div>
</template>

<script>
import Card from '@/components/Card.vue';

export default {
  name: 'home',
  components: {
    Card,
  },
  mounted() {
    // window.addEventListener('beforeunload', e => this.beforeunloadFn(e));

    const svgLinks = [];
    const pngLinks = [];
    for (let i = 1; i <= 100; i += 1) {
      if (i < 10) {
        svgLinks.push(`/people/svg/gee_me_00${i}.svg`);
        pngLinks.push(`/people/png/gee_me_00${i}.png`);
      } else if (i >= 10 && i < 100) {
        svgLinks.push(`/people/svg/gee_me_0${i}.svg`);
        pngLinks.push(`/people/png/gee_me_0${i}.png`);
      } else {
        svgLinks.push(`/people/svg/gee_me_${i}.svg`);
        pngLinks.push(`/people/png/gee_me_${i}.png`);
      }
    }
    this.svgs = svgLinks;
    this.pngs = pngLinks;
  },
  // methods: {
  //   beforeunloadFn() {
  //     window.scrollTo(0, 0, 'auto');
  //   },
  // },
  // destroyed() {
  //   window.removeEventListener('beforeunload', e => this.beforeunloadFn(e));
  // },
  data() {
    return {
      svgs: this.svgLinks,
      pngs: this.pngLinks,
    };
  },
};
</script>

<style lang="scss" scoped>
@import '../style/global.scss';

.home {
  position: relative;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: space-between;

  .side-panel {
    position: fixed;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    max-width: calc(440px - 20px);
    width: 100%;
    height: calc(100vh - 40px);
    padding: 40px;
    margin: 20px;

    &_top {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100%;
      margin-top: -84px;

      .logo {
        position: relative;
        left: 20px;
        height: 54px;
        margin-bottom: 32px;
      }

      p {
        max-width: 360px;
        text-align: center;
        @include font(16, 400, 21, 0);
      }
      a {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 48px;
        border-radius: 4px;
        text-decoration: none;
        transition: all 0.25s ease;
        @include font(16, 600, 16, 0);

        img {
          width: 24px;
          margin-right: 16px;
        }

        &:nth-of-type(1) {
          color: white;
          background-color: $color-black-1;
          margin-top: 80px;
          margin-bottom: 20px;

          &:hover {
            color: $color-black-1;
            background-color: white;
            border: 1px solid $color-black-1;
          }
        }
        &:nth-of-type(2) {
          color: $color-black-1;
          background-color: white;
          border: 1px solid $color-black-1;

          &:hover {
            color: white;
            background-color: $color-black-1;
          }

          img {
            margin-left: -7px;
          }
        }
      }
    }

    &_bottom {
      width: 100%;
      display: flex;
      flex-direction: column;

      span {
        &:nth-of-type(1) {
          margin-bottom: 10px;
          @include font(12, 400, 12, 0);
        }
        &:nth-of-type(2) {
          margin-bottom: 10px;
          @include font(12, 400, 12, 0);
        }
        &:nth-of-type(3) {
          @include font(12, 400, 12, 1);
          a {
            &:hover {
              text-decoration: underline;
            }
          }
        }
      }

      .links {
        a {
          @include font(14, 400, 14, 0);

          &:hover {
            text-decoration: underline;
          }
        }

        span {
          margin: 0 8px;
          @include font(14, 400, 14, 0);
        }
        margin-bottom: 20px;
      }

      .social {
        display: flex;
        margin-bottom: 40px;

        a {
          height: 40px;
          transition: all 0.25s ease;

          &:nth-of-type(1) {
            img {
              width: 185px !important;
              height: 40px !important;
            }

            &:hover {
              filter: invert(1) hue-rotate(96deg) grayscale(1) contrast(1)
                brightness(2);
            }
          }

          &:nth-of-type(2),
          &:nth-of-type(3) {
            width: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            border: 1px solid;
            border-radius: 7px;
          }
          &:nth-of-type(2) {
            border-color: #c32361;
            margin: 0 10px;

            &:hover {
              background-color: rgba(217, 89, 136, 0.2);
              border-color: transparent;
            }
          }
          &:nth-of-type(3) {
            border-color: #161516;

            &:hover {
              background-color: rgba(22, 21, 22, 0.1);
              border-color: transparent;
            }
          }
        }
      }
    }
  }

  .container {
    position: absolute;
    right: 60px;
    width: calc(100vw - 520px);
    padding: 20px 20px 20px 0;
    display: grid;
    grid-template-rows: repeat(25, 360px);
    grid-template-columns: repeat(4, 25%);
    grid-row-gap: 20px;
    grid-column-gap: 20px;
  }
}

@media screen and (min-width: 1950px) {
  .container {
    grid-template-rows: repeat(17, 390px) !important;
    grid-template-columns: repeat(6, 16.36%) !important;
  }
}

@media screen and (max-width: 1450px) {
  .container {
    grid-template-rows: repeat(25, 320px) !important;
    grid-template-columns: repeat(4, 34.33%) !important;
  }
}
@media screen and (max-width: 1050px) {
  .container {
    grid-template-rows: repeat(50, 320px) !important;
    grid-template-columns: repeat(2, 54.8%) !important;
  }
}
@media screen and (max-width: 900px) {
  .container {
    grid-template-rows: repeat(100, 340px) !important;
    grid-template-columns: repeat(1, calc(100% + 60px)) !important;
  }
}
@media screen and (max-width: 700px) {
  .home {
    height: auto;
    flex-direction: column;
    flex-wrap: wrap;
    align-items: center;

    .side-panel {
      position: relative;
      margin: 0;
      padding: 0 32px 32px 32px;
      height: 100vh;

      .side-panel_top {
        margin: 0;
        padding: 0px;

        a {
          &:nth-of-type(1) {
            margin-top: 48px;
          }
        }
      }
    }

    .container {
      width: 100vw;
      position: unset;
      grid-template-rows: repeat(50, 220px) !important;
      grid-template-columns: repeat(2, calc(50% - 10px)) !important;
      padding: 20px;
    }
  }
}
.card {
  opacity: 0;
  backface-visibility: hidden;
  /* transform: translateY(60px); */
  animation: cardShow 0.35s ease forwards;

  @keyframes cardShow {
    to {
      opacity: 1;
      /* transform: translateY(0); */
    }
  }
  @for $i from 1 through 100 {
    &:nth-of-type(#{$i}) {
      $timing: $i * 0.06;
      animation-delay: #{$timing}s;

      ::v-deep img {
        $timing: $i * 0.07;
        animation-delay: #{$timing}s;
      }
    }
  }
}
</style>
