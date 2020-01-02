<template>
  <div class="home">
    <div class="side-panel">
      <div class="side-panel_top">
        <img class="logo" src="../assets/logo.svg" alt srcset />
        <!--eslint-disable -->
        <p>Character Kit is a completely free collection of coaxial cartoon characters with 80 levels of images and more than 400 head / wearing parts, which can be arbitrarily matched with the image you want. You can use it in any design or development project. The casual style is widely applicable.</p>
        <!--eslint-enable -->
        <a download href>
          <img src="../assets/Sketch_Logo.svg" alt />
          Sketch
        </a>
        <a href target="_blank">
          <img src="../assets/Figma_Logo.svg" alt />
          Figma
        </a>
      </div>
      <div class="side-panel_bottom">
        <span>Designers</span>
        <div class="links">
          <a target="_blank" href>Yorkun</a>
          <span>/</span>
          <a target="_blank" href>Hwoma</a>
          <span>/</span>
          <a target="_blank" href>Yancy Min</a>
          <span>/</span>
          <a target="_blank" href>Charlie Liu</a>
        </div>
        <div class="social">
          <a
            href="https://www.producthunt.com/posts/ouch-illustrations?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-ouch-illustrations"
            target="_blank"
          >
            <img
              src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=141557&theme=light"
              alt="Ouch! Illustrations - Free illustrations for better UX | Product Hunt Embed"
              style="width: 250px; height: 54px;"
              width="250px"
              height="54px"
            />
          </a>
          <a href="https://dribbble.com/geetest" target="_blank">
            <img src="../assets/dribbble.svg" alt />
          </a>
          <a href="https://dribbble.com/geetest" target="_blank">
            <img src="../assets/github.svg" alt />
          </a>
        </div>
        <span>Made with ❤️ in Wuhan</span>
        <span>
          Copyright © 2020
          <a href="https://geetest.design" target="_blank">G-Design</a>
        </span>
      </div>
    </div>
    <div class="container">
      <Card v-for="(c,index) in svgs" :svgSrc="svgs[index]" :key="index" />
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
    const svgLinks = [];
    for (let i = 1; i <= 80; i += 1) {
      svgLinks.push(`/people/0${i}.svg`);
    }
    this.svgs = svgLinks;
  },
  data() {
    return {
      svgs: this.svgLinks,
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
        left: 14px;
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
        align-items: center;
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
    grid-template-rows: repeat(20, 360px);
    grid-template-columns: repeat(4, 25%);
    grid-row-gap: 20px;
    grid-column-gap: 20px;
  }
}

@media screen and (min-width: 1920px) {
  .container {
    grid-template-rows: repeat(14, 420px) !important;
    grid-template-columns: repeat(6, 16.36%) !important;
  }
}
@media screen and (max-width: 1600px) {
  .container {
    grid-template-rows: repeat(16, 360px) !important;
    grid-template-columns: repeat(5, 19.67%) !important;
  }
}
@media screen and (max-width: 1400px) {
  .container {
    grid-template-rows: repeat(27, 320px) !important;
    grid-template-columns: repeat(3, 34.33%) !important;
  }
}
@media screen and (max-width: 1050px) {
  .container {
    grid-template-rows: repeat(40, 320px) !important;
    grid-template-columns: repeat(2, 54.8%) !important;
  }
}
@media screen and (max-width: 900px) {
  .container {
    grid-template-rows: repeat(80, 340px) !important;
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
      grid-template-rows: repeat(40, 220px) !important;
      grid-template-columns: repeat(2, calc(50% - 10px)) !important;
      padding: 20px;
    }
  }
}
</style>
