<script >
import { RouterLink, RouterView } from 'vue-router'
import NetHomePage from './NetHomePage.vue';

export default {
  components: {
    RouterLink,
    NetHomePage
  }
}
</script>
<template>
  <NetHomePage />

  <div class="header icon page">
    <div class="m1 ">
      <img src="../../public/博客來圖片/8.jpg" alt="" class="p1">
      <a href="#">博客來火鍋</a>
    </div>
    <div class="m2 x">
      <i class="fa-solid fa-house  "></i><a href="#">品牌介紹</a>
    </div>
    <div class="m3 x">
      <i class="fa-solid fa-bookmark x"></i>
      <a href="">美味菜單</a>
    </div>
    <div class="m4 x">
      <i class="fa-solid fa-location-dot"></i>
      <a href="#">店鋪資訊</a>
    </div>
    <div class="m5 x">
      <i class="fa-solid fa-users"></i>
      <a href="#">人才招募</a>
    </div>



  </div>
<div class="second page">
  <div class="left">
    <div class="carousel">

<div id="carouselExampleCaptions" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active"
      aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1"
      aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2"
      aria-label="Slide 3"></button>
  </div>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="../../public/博客來圖片/1.jpg " class="d-block w-100 ">
      <div class="carousel-caption d-none d-md-block">
        <h5></h5>
      </div>
    </div>
    <div class="carousel-item">
      <img src="../../public/博客來圖片/4.jpg" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <h5></h5>
      </div>
    </div>
    <div class="carousel-item">
      <img src="../../public/博客來圖片/6.jpg" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <h5></h5>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions"
    data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions"
    data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
    </div>

      </div>
    </div>
    <div class="right">
      <i class="fa-solid fa-shop u">關於店家</i>

      <p>❤️西螺“博客來火鍋肉片通通吃到飽“成人只要339元”“不收服務費”牛肉、羊肉、豬肉、豬培根、火鍋料，熟食、湯包、蒸餃、燒賣、珍珠丸，炸物，飲料，冰淇淋，冰棒（請勿浪費食材），歡迎提早預約呦，
        吃鍋最怕鍋中有你不愛吃的食物
        大致芋頭，小至金針菇
        想要鍋裡每樣都是你的最愛❤️
        來“博客來火鍋”多樣食材，
        直接挑你最愛的下鍋就對啦！
        吃火鍋何必東挑西挑👈
        離峰時段,若沒客人🕣，會提早打烊，
        如需用餐請先電話確認☎️
        竭誠歡迎您的光臨～❤
        西螺鎮公正一路101～6號
        訂位電話～055873787，吃好，睡飽，心情好
        #火鍋吃到飽美食平價消費午餐晚餐炸物冰淇淋港式點心飲料吃飯餐廳

      </p>
      <div class="seeMoreArea">
        <a href="#">顯示更多</a>
      </div>
    </div>

  </div>



  <div class="third page">

  </div>

  <div class="fourth page">

  </div>
  <div class="footer page">

  </div>
</template>

<style>
.page {
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
}

.icon {
  font-size: 30pt;
}

.x {
  border-radius: 20px;
  padding: 0.5rem;
  transition: all 0.5s ease;

  &:hover {
    background-color: rgba(118, 118, 117, 0.5);
  }

}

a {
  text-decoration: none;
  font-size: 20pt;
}

.header {
  z-index: 2;
  background-color: white;
  display: flex;
  justify-content: space-around;
  align-items: center;
  border: 0px solid black;
  height: 15vh;
  position: relative;
  backdrop-filter: blur(20px);
  box-shadow: 0px 10px 6px 0px #777;
  backdrop-filter: blur(20px);

  .p1 {
    height: 100px;
    width: 100px;
    object-position: 0rem 0rem;
  }
}

.second {
  display: flex;
  margin: 30px;

  .left {
    height: 90vh;
    width: 200vw;
    border: 0px solid black;
  }

  .right {
    .u {
      margin: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 30pt
    }

    margin: 50px;
    height: 80vh;
    flex-direction: column;
    border: 0px solid black;

    .seeMoreArea {
      display: flex;
      line-height: 3rem;
      transition: all 0.5s ease;

      &:hover {
        a {
          color: rgba(250, 86, 86, 0.8);
          scale: 1.2;

          &::after {
            border-bottom-color: rgba(250, 86, 86, 0.8);
          }
        }
      }
    }
  }
}</style>