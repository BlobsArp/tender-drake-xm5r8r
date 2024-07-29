<template>
  <div id="app">
    <div class="photo-colle">
      <div class="photo-colle__title">
        <h1>
          <a target="_blank" href="https://www.instagram.com/esdesigntpe/"
            >Pump.fun</a
          >
          <a target="_blank" href="https://www.threads.net/@esdesigntpe"
            >Telegram</a
          >
        </h1>
        <img src="https://i.imgur.com/VVTrdJs.png" alt="" />
      </div>
      <div class="photo-colle__wrap" ref="photoColleWrap">
        <section
          class="photo-colle__gallery"
          v-for="(group, idx) in pageData"
          :key="idx"
        >
          <div
            class="photo-colle__gallery-item"
            v-for="item in group"
            :key="item.id"
          >
            <figure @click="clickScrollToImgTop">
              <video
                v-if="item.type"
                preload
                autoplay="autoplay"
                loop="loop"
                playsinline=""
                muted=""
              >
                <source :src="item.url" type="video/mp4" />
              </video>
              <img v-else :src="item.url" />
            </figure>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const pageData = ref([
  [
    {
      url:
        "https://steamuserimages-a.akamaihd.net/ugc/365155533179982937/7ACEE678AE01F2852FF196B084AFE6C9FE786D13/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false",
    },
    {
      url: "https://i.imgur.com/MNJV6jX.jpeg",
    },
    {
      url:
        "https://www.pbh2.com/wordpress/wp-content/uploads/2013/05/cutest-cat-gifs-kitten-heads.gif",
    },
    {
      url: "https://i.imgur.com/OiG1uwk.jpeg",
    },
    {
      url:
        "https://t3.ftcdn.net/jpg/05/94/98/82/360_F_594988297_E9ZBkFWJt6HuaKAws9W9kCBSvLPWk7PR.jpg",
    },
    {
      url:
        "https://i.pinimg.com/originals/e9/8a/08/e98a086e973cdd9fab00d472c23396e2.gif",
    },
    {
      url:
        "https://qph.cf2.quoracdn.net/main-qimg-594dad760d499c7071f3f22afa1a39ad",
    },
    {
      url: "https://i.gifer.com/76S3.gif",
    },
    {
      url: "https://i.imgur.com/QS5x453.jpeg",
    },
    {
      url:
        "https://dwgyu36up6iuz.cloudfront.net/heru80fdn/image/upload/c_fill,d_placeholder_thenewyorker.png,fl_progressive,g_face,h_1080,q_80,w_1920/v1522075014/thenewyorker_obsessions-how-cats-tamed-us.jpg",
    },
    {
      url:
        "https://i.pinimg.com/originals/5e/c3/6c/5ec36cd7f15957387a7afae190e94673.jpg",
    },
  ],
  [
    {
      url:
        "https://media1.tenor.com/m/-qBsG1HwR4oAAAAC/cat-dance-dancing-cat.gif",
    },
    {
      url:
        "https://cdn.shopify.com/s/files/1/0344/6469/files/cat-gif-loop-maru_grande.gif?v=1523984148",
    },
    {
      url:
        "https://i.guim.co.uk/img/media/43352be36da0eb156e8551d775a57fadba8ae6d7/0_0_1440_864/master/1440.jpg?width=1200&height=1200&quality=85&auto=format&fit=crop&s=1829611852af3ffc6460b4068e20bcbc",
    },
    {
      url:
        "https://hips.hearstapps.com/hmg-prod/images/cute-cat-photos-1593441022.jpg?crop=0.670xw:1.00xh;0.167xw,0&resize=640",
    },
    {
      url: "https://www.litter-robot.com/media/wysiwyg/kindle-kittens.png",
    },
    {
      url:
        "https://soranews24.com/wp-content/uploads/sites/3/2014/12/cs-3.png?w=580",
    },
    {
      url: "https://img.tfd.com/art/Group_of_Cats_Clowder.jpg",
    },
    {
      url:
        "https://icatcare.org/app/uploads/2020/02/unowned-cats-7-1200x630.jpg",
    },
    {
      url:
        "https://i.natgeofe.com/k/bdae4b07-8472-4d41-983a-21275fa95ebd/a-8-animal-group-names-glaring-of-cats_16x9.jpg",
    },
    {
      url:
        "https://www.todayifoundout.com/wp-content/uploads/2010/03/kittens2.jpg",
    },
    {
      url:
        "https://qph.cf2.quoracdn.net/main-qimg-c1fc49fc6ffacaeda4643917893f3886-lq",
    },
  ],
  [
    {
      url:
        "https://www.catster.com/wp-content/uploads/2023/11/feral-cats-resting-outdoor_Dmitris-Vetsikas_Pixabay.jpg",
    },
    {
      url:
        "https://www.rover.com/blog/wp-content/uploads/group-of-cats-friendly-cats-at-home-e1682866860855.jpg",
    },
    {
      url:
        "https://www.loveyourcat.com/wp-content/uploads/2023/12/lots-of-stray-cats-wandering-around-an-ally-jpg-1024x569.jpg",
    },
    {
      url:
        "https://preview.redd.it/if-soad-was-a-group-of-cats-v0-myabb9okgg7c1.jpeg?auto=webp&s=2b1f6039d3bae85ecafc02c8d709bbd19dc2ebfe",
    },
    {
      url:
        "https://www.warrenphotographic.co.uk/photography/bigs/07572-Group-of-Cats-around-a-childs-chair-white-background.jpg",
    },
    {
      url: "https://media1.tenor.com/m/5BYK-WS0__gAAAAd/cool-fun.gif",
    },
    {
      url:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSwWhmo4N3JQlwQcVdwamknRlGqWEXxX6xrFA&s",
    },
    {
      url:
        "https://media.istockphoto.com/id/498805012/photo/five-cute-kittens-in-braided-basket.jpg?s=612x612&w=0&k=20&c=pYoONf1iRoR1j2_Xl5bpEcqB30eAgvY0o1vhMDMUXR8=",
    },
    {
      url: "https://www.icegif.com/wp-content/uploads/2024/01/icegif-1086.gif",
    },
    {
      url:
        "https://preview.redd.it/a-group-of-soldier-cats-take-a-victory-selfie-after-v0-4bgcxmj4t1qa1.jpg?width=640&crop=smart&auto=webp&s=c520c0972fb1a64d0db6c43db727f9e22d921673",
    },
    {
      url:
        "https://asiangroupcatsociety.co.uk/wp-content/uploads/2021/08/cropped-darnakittens.jpg",
    },
  ],
  [
    {
      url:
        "https://media1.popsugar-assets.com/files/thumbor/5TQCAiGvLPit9WBwm2JhrLCc_Xo=/fit-in/330x225/top/filters:format_auto():upscale()/2015/08/18/672/n/1922243/82359bd1a4564340_catgif4.gif",
    },
    {
      url:
        "https://st.depositphotos.com/13846464/54248/i/450/depositphotos_542486528-stock-photo-paphos-cyprus-january-2022-abandoned.jpg",
    },
    {
      url:
        "https://cdn.create.vista.com/api/media/small/22890862/stock-photo-group-of-cats",
    },
    {
      url:
        "https://img.freepik.com/premium-photo/group-cats-with-white-background_1041339-3.jpg",
    },
    {
      url:
        "https://qph.cf2.quoracdn.net/main-qimg-85879eac85a37e54a16bc51802b1dab7",
    },
    {
      url:
        "https://31.media.tumblr.com/01005f7fa8b54c2a1b0eef5ba9d44e16/tumblr_myl0misl141s199fdo1_500.gif",
    },
    {
      url:
        "https://www.economist.com/cdn-cgi/image/width=1424,quality=80,format=auto/content-assets/images/20230617_STP001.jpg",
    },
    {
      url:
        "https://qph.cf2.quoracdn.net/main-qimg-e3f8b068414dac26515228a24cfe52fc-lq",
    },
    {
      url:
        "https://steamuserimages-a.akamaihd.net/ugc/365155533179982937/7ACEE678AE01F2852FF196B084AFE6C9FE786D13/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false",
    },
    {
      url:
        "https://animalcorner.org/wp-content/uploads/2022/10/What-is-a-group-of-cats-called-8534329.png",
    },
    {
      url:
        "https://t4.ftcdn.net/jpg/07/49/99/45/360_F_749994515_zxdXGdEn2SKHrwirJ2VBAiGFcJgsLCLo.jpg",
    },
  ],
]);

const photoColleWrap = ref();
let scrollListener = null;
const clickScrollToImgTop = (e) => {
  const imgRect = e.target.getBoundingClientRect();
  const viewportHeight = window.innerHeight;

  const scaleValue = (viewportHeight / imgRect.height) * 0.96;

  const centerOfImgPositionTop =
    window.scrollY + imgRect.top + imgRect.height / 2;
  const centerOfImgPositionLeft = imgRect.left + imgRect.width / 2;

  const winCenterX = window.innerWidth / 2;
  const winCenterY = window.innerHeight / 2;

  const orignY =
    (centerOfImgPositionTop / photoColleWrap.value.clientHeight) * 100;
  const orignX =
    (centerOfImgPositionLeft / photoColleWrap.value.clientWidth) * 100;

  // const moveX = imgRect.width * scaleValue
  const imgWinCenterY = imgRect.top + imgRect.height / 2 - winCenterY;
  const imgWinCenterX = imgRect.left + imgRect.width / 2 - winCenterX;

  // photoColleWrap.value.style.transform = `translate3d(${-imgWinCenterX}px, ${-imgWinCenterY}px, 0)`;

  photoColleWrap.value.style.left = `${-imgWinCenterX}px`;
  photoColleWrap.value.style.top = `${-imgWinCenterY}px`;
  photoColleWrap.value.style.transformOrigin = `${orignX}% ${orignY}%`;
  photoColleWrap.value.style.transform = `scale(${scaleValue})`;

  // 設定延遲以避免立即取消放大
  setTimeout(() => {
    if (!scrollListener) {
      scrollListener = true; // 標記已添加監聽器
      window.addEventListener("scroll", handleScroll);
    }
  }, 300);
};

const handleScroll = () => {
  // console.log('close');
  photoColleWrap.value.style.left = `0px`;
  photoColleWrap.value.style.top = `0px`;
  photoColleWrap.value.style.transform = `scale(1)`;
  scrollListener = null;
};
</script>

<style lang="scss">
@mixin size($w, $h: $w) {
  width: $w;
  height: $h;
}
body {
  width: 100%;
  background: #000;
  color: #fff;

  a {
    color: #fff;
    text-decoration: none;
  }
}
.photo-colle {
  &__title {
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    position: fixed;
    z-index: 90;
    mix-blend-mode: difference;

    > h1 {
      text-align: center;
      font-size: 23px;
      font-weight: 300;
      line-height: 1.4;

      a {
        color: #FF00C7;
      }
    }

    img {
      width: auto;
      height: 15vh;
      pointer-events: none;
      position: absolute;
      left: -20vh;
    }
  }

  &__wrap {
    left: 0;
    top: 0;
    min-height: 100vh;
    transition: transform 0.6s, left 0.6s, top 0.6s;
    transform-origin: 0 0;
    position: relative;
  }

  &__gallery {
    top: 0;
    left: 0;
    height: 1500px;
    display: grid;
    grid-template-columns: repeat(10, 1fr);
    grid-template-rows: repeat(8, 1fr);
    grid-column-gap: 10px;
    grid-row-gap: 10px;
    margin-bottom: 10px;

    &-item {
      figure {
        width: 100%;
        height: 100%;
        position: relative;
        overflow: hidden;
        cursor: pointer;
        margin: 0;
        border: 1px solid #000;
        transition: border-color 0.2s;

        img,
        video {
          width: 100%;
          height: 100%;
          position: absolute;
          left: 0;
          top: 0;
          object-fit: cover;
          transition: opacity 0.6s;
          // opacity: 0;
        }
        &.is-inview {
          img {
            opacity: 1;
          }
        }

        &:hover {
          border-color: #FF00C7;
        }
      }

      @for $i from 1 through 11 {
        &:nth-child(11n + #{$i}) {
          @for $i from 1 through 11 {
            &:nth-child(11n + #{$i}) {
              @if $i == 1 {
                grid-area: 1 / 1 / 5 / 5;
              } @else if $i == 2 {
                grid-area: 1 / 5 / 3 / 7;
              } @else if $i == 3 {
                grid-area: 1 / 7 / 3 / 9;
              } @else if $i == 4 {
                grid-area: 1 / 9 / 3 / 11;
              } @else if $i == 5 {
                grid-area: 3 / 5 / 5 / 7;
              } @else if $i == 6 {
                grid-area: 3 / 7 / 7 / 11;
              } @else if $i == 7 {
                grid-area: 5 / 1 / 7 / 3;
              } @else if $i == 8 {
                grid-area: 7 / 1 / 9 / 3;
              } @else if $i == 9 {
                grid-area: 5 / 3 / 9 / 7;
              } @else if $i == 10 {
                grid-area: 7 / 7 / 9 / 9;
              } @else if $i == 11 {
                grid-area: 7 / 9 / 9 / 11;
              }
            }
          }
        }
      }
    }
  }
}
</style>