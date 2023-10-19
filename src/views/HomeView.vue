<script >
import { RouterLink, RouterView } from 'vue-router'
import bg2 from '../components/bg2.vue';

export default {
  data() {
    return {
      imageUrl: null,
      isZoomed: false,
      currentDate: new Date().toLocaleString(),
      musicSource: '../../public/mp3/fripSide - double Decades(Audio).mp3', // 歌曲文件的路径，请根据实际情况修改路径

      currentSongIndex: 0,
      songs: [
        {
          title: "fripSide - double Decades(Audio)",
          image: "../../public/mp3/mp3圖/01.jpg",
          audioSource: "../../public/mp3/song1.mp3"
        },
        {
          title: "藍井エイル「シューゲイザー」Music Video",
          image: "../../public/mp3/mp3圖/02.jpg",
          audioSource: "../../public/mp3/song1.mp3"
        },
        // 添加更多歌曲
      ],
      
    }
  },
  components: {
    RouterLink,
    RouterView,
    bg2,
   
  },
  created() {
    // 在组件创建时启动日期更新
    this.updateDate();
  },
  computed: {
    currentSong() {
      return this.songs[this.currentSongIndex];
    },
  },
  methods: {
    updateDate() {
      // 更新当前日期和时间
      this.currentDate = new Date().toLocaleString();
      // 每秒更新一次
      setTimeout(this.updateDate, 1000);
    },
    playSound() {
      const audio = new Audio("../../public/mp3/keypress.mp3"); // 替换为您的声音文件路径
      audio.play();
    },
     playMusic() {
      this.$refs.audioPlayer.play();
    },
    
    playPreviousSong() {
      this.currentSongIndex = (this.currentSongIndex - 1 + this.songs.length) % this.songs.length;
      this.$refs.audioPlayer.load();
      this.$refs.audioPlayer.play();
    },
    playNextSong() {
      this.currentSongIndex = (this.currentSongIndex + 1) % this.songs.length;
      this.$refs.audioPlayer.load();
      this.$refs.audioPlayer.play();
    },
  },
};






</script>

<template>
  <div class="userPage">
    <div class="bg2-container" >
    <!-- <bg2></bg2> -->

    </div>
    <div class="userLeft">
      <div class="userLeftTop">
        <div class="date-display">
          <p>{{ currentDate }}</p>
        </div>
      </div>
      <div class="userLeftDown">

      </div>
    </div>
    <div class="userMid">

      <div class="midTopTeam"><RouterLink class="routerItemBlack" @mouseover="playSound" to="/實驗">
        <div class="midTop1" >
          <br>
          漫画、イラスト</div></RouterLink>
          
      
         
        

          <RouterLink class="routerItemWhite" @mouseover="playSound" to="/components/BlogHeader">
                    <div class="midTop2">
          <br>ブログ </div></RouterLink>

          
       

          <RouterLink class="routerItemBlue" @mouseover="playSound" to="/components/NetHomePage">
                   <div class="midTop3" >
          <br> ウェブサイト</div></RouterLink>
   
      </div>
      <div class="midBetween ">
        <img src="./../../public/7.jpg" alt="">
        <div class="midBetweenright">
          <h3>自己紹介</h3>
          <h6>
            はじめまして、リャオエンミンと申します。お貴重な時間をいただき、ありがとうございます。本日はよろしくお願い致します。私は現職で、レストラン業の社員として働いています、もう4年間ほど勤めています。仕事が終わった後は、学校で電動自転車のモーターの取り付けや屋内配線など、さまざまな電気機器の組み立てや修理を学びました。それで私は台湾で4年間勉強した後、最近卒業しました。休暇の際、私は自分で中古の古いバイクを修理し、そしてバイクのエンジンも組み立てることもできます。それから、趣味はエレギタを弾ける、特に日本のバンドが聴いています。普段のところ漫画関するイラストの作品を描くこと。そして写真を撮り、いつか日本でバイクに乗って様々な場所の景色を見って、有名な場所に行きたいと考えています。
            
            
          </h6>
          <a href="https://www.instagram.com/zz025784/">Insta:@zz025784 </a>
          <a href="https://twitter.com/kamishu0126">Twitter:@kamishu0126</a>
          <br>
          <h3>実行しなければ、ただの夢でしかない。</h3>
        </div>

      </div>
      <div class="midDownTeam">
        <div class="midDown1">
          <iframe width="427px" height="203px" src="https://www.youtube.com/embed/Ci_zad39Uhw?si=4FZgs2QmMA-7mTPG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

        </div>
        <div class="midDown2">
          

          <button  class="Btn1">
          <img src="../../public/LOGO1.png" alt="">

      
    <source :src="videoSource" type="video/mp4" />
        </button>
        
        </div>
      </div>
    </div>
    <div class="userRight">
      <div class="userRightTop">
        <div>
    <img :src="currentSong.image" alt="Album Cover" />
    <div>
      <h2>{{ currentSong.title }}</h2>
      <p>{{ currentSong.artist }}</p>
    </div>
    <audio loop="loop" start:0.5  ref="audioPlayer" :src="musicSource"   controls autoplay ></audio>    
        <button @click="playPreviousSong">上一首</button>
    <button @click="playNextSong">下一首</button>
  </div>
      </div>

      <div class="userRightDown">
        <div class="login-box">
  <h2>ログイン画面</h2>
  <form>
    <div class="user-box" @click="playVideo">
      <input type="text" name="" required="" >
      <label>メール</label>
    </div>
    <div class="user-box" >
      <input type="text"  class=""  name="" required="">
      <label>パスワード</label>
    </div>
    <a href="#" >
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      ログイン
    </a>
  </form>
</div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
$mainColor:#2f8fd9;
a {
  text-decoration: none;
}.routerItemWhite{
  color: none;
  font-size: 28pt;
 &:hover{
  color: white;
 }
}
.routerItemBlue{
  font-size: 28pt;&:hover{
  color: white;
 }
}
.routerItemBlack{
  font-size: 28pt;
  color: black;
}
.userPage  {
  margin: 20px;
  display: flex;
  border: 0px solid black;
  height: 100vh;
  width: 100vw;
  
  .bg2-container {
    background-color: rgb(255, 255, 255); /* 透明背景 */
    position: absolute;
    top: 0;
    left: 0;
    height: 100vh;
  width: 100vw; /* 设置高度为 100% */
    z-index:-1; /* 确保 bg1 在最底层 */

    display: flex; 
    align-items: center; 
    
}
 

  .userLeft {
    border: 0px solid black;
    height: 97vh;
    width: 20vw;

    .userLeftTop {
      background-color: rgb(255, 255, 255); /* 透明背景 */

      border: 2px solid black;
      height: 47vh;
      width: 19vw;
      transition: 0.3s;
      box-shadow: 0px 5px 10px 0px #777;
      .date-display {
        
        border: 0px solid black;

        font-size: 2.2em;

        .time {
          font-family: "Arial", sans-serif;

        }
      }

    }

    .userLeftDown {
      background-color: rgb(255, 255, 255); /* 透明背景 */

      margin-top: 10px;
      border: 2px solid black;
      height: 46vh;
      width: 19vw;
      box-shadow: 0px 5px 10px 0px #777;
    }
  }

  .userMid {
    height: 95vh;
    width: 58vw;
    border: 0px solid rgb(6, 6, 6);

    .midTopTeam {
      height: 20vh;
      display: flex;
      justify-content: space-around;

      .midTop1 {
        background-color: rgb(255, 255, 255); /* 透明背景 */

        height: 20vh;
        width: 19vw;
        border: 2px solid rgb(6, 6, 6);
        transition: 0.8s;
        box-shadow: 0px 5px 10px 0px #777;
        &:hover {
         
         transition: 0.8s;
              background-image: url("../../public/首頁/3.jpg");
                transform:translateY(-15px);
                background-size: cover;
                
                }
      }

      .midTop2 {
        background-color: rgb(255, 255, 255); /* 透明背景 */

        height: 20vh;
        width: 19vw;
        border: 2px solid rgb(6, 6, 6);
        transition: 0.8s;
        box-shadow: 0px 5px 10px 0px #777;
            &:hover {color: #ffffff;
              background-image: url("../../public/首頁/1.jpg");
              background-size: cover;
                transform:translateY(-15px);
                
                }
      }

      .midTop3 {
        background-color: rgb(255, 255, 255); /* 透明背景 */
        color: black;
        height: 20vh;
        width: 19vw;
        border: 2px solid rgb(6, 6, 6);
        transition: 0.5s;
        box-shadow: 0px 5px 10px 0px #777;
            &:hover {
              background-image: url("../../public/首頁/2.jpg");
              background-size: cover;
       
              color: #4885ff;
                transform:translateY(-15px);
                }
      }
    }


    .midBetween {
      
      height: 46vh;
      margin-top: 10px;
      display: flex;
      border: 2px solid rgb(6, 6, 6);
      transition: 0.5s;
      background-color: rgb(255, 255, 255);
      box-shadow: 0px 5px 10px 0px #777;
      
      &:hover {
        transform: scale(1.2, 1.2);
      }

      img {

        width: 20vw;
        height: 45vh;
        border: 2px solid rgb(6, 6, 6);

      }

      .midBetweenright {
        margin: 10px;

        a {
          font-size: 20pt;
          text-decoration: none;

        }
      }
    }

    .midDownTeam {
      margin-top: 10px;
      height: 31vh;
      display: flex;

      border: 0px solid rgb(6, 6, 6);

      .midDown1 {

        width: 28vw;
        height: 26vh;
        border: 2px solid rgb(6, 6, 6);
        box-shadow: 0px 5px 10px 0px #777;
      }

      .midDown2 {
        margin-left: 5px;
        width: 36vw;
        height: 26vh;
        border: 2px solid rgb(0, 0, 0);
      background-color: white;
        overflow: hidden; 
        z-index: -1;
        box-shadow: 0px 5px 10px 0px #777;
        .Btn1{  border: 0px solid rgb(0, 0, 0);
          bottom: 18%;
          background-color: white;
          position: relative; 
         
      
      }
      }
    }

  }

  .userRight {
    margin-left: 10px;
    height: 97vh;
    width: 18vw;
    border: 0px solid black;

    .userRightTop {
      background-color: rgb(255, 255, 255); /* 透明背景 */

      border: 2px solid black;
      height: 55vh;
      box-shadow: 0px 5px 10px 0px #777;
      overflow: hidden;

    }

    .userRightDown {
      
      margin-Top: 10px;
      border: 2px solid black;
      height: 38vh;
      box-shadow: 0px 5px 10px 0px #777;

     

      .login-box {
  position: relative;
  right: -50%;
  top: 50%;
  width: 300px;
  padding: 40px;
  transform: translate(-50%, -50%);
  box-sizing: border-box;
  border-radius: 10px;overflow: hidden;
}

.login-box h2 {
 
  padding: 0;
  color: $mainColor;
  text-align: center;
}

.login-box .user-box {
  position: relative;
}

.login-box .user-box input {
  width: 100%;
  padding: 10px 0;
  font-size: 16px;
  color: $mainColor;
  margin-bottom: 30px;
  border: none;
  border-bottom: 1px solid $mainColor;
  outline: none;
  background: transparent;
}
.login-box .user-box label {
  position: absolute;
  top:0;
  left: 0;
  padding: 10px 0;
  font-size: 16px;
  color:  $mainColor;
  pointer-events: none;
  transition: .5s;
}

.login-box .user-box input:focus ~ label,
.login-box .user-box input:valid ~ label {
  top: -20px;
  left: 0;
  color: #03e9f4;
  font-size: 12px;
}

.login-box form a {
  position: relative;
  display: inline-block;
  padding: 10px 20px;
  color: #03e9f4;
  font-size: 16px;
  text-decoration: none;
  text-transform: uppercase;
  overflow: hidden;
  transition: .5s;
  margin-top: 40px;
  letter-spacing: 4px
}

.login-box a:hover {
  background: #03e9f4;
  color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 5px #03e9f4,
              0 0 25px #03e9f4,
              0 0 50px #03e9f4,
              0 0 100px #03e9f4;
}

.login-box a span {
  position: absolute;
  display: block;
}

.login-box a span:nth-child(1) {
  top: 0;
  left: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, #03e9f4);
  animation: btn-anim1 1s linear infinite;
}

@keyframes btn-anim1 {
  0% {
    left: -100%;
  }
  50%,100% {
    left: 100%;
  }
}

.login-box a span:nth-child(2) {
  top: -100%;
  right: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(180deg, transparent, #03e9f4);
  animation: btn-anim2 1s linear infinite;
  animation-delay: .25s
}

@keyframes btn-anim2 {
  0% {
    top: -100%;
  }
  50%,100% {
    top: 100%;
  }
}

.login-box a span:nth-child(3) {
  bottom: 0;
  right: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(270deg, transparent, #03e9f4);
  animation: btn-anim3 1s linear infinite;
  animation-delay: .5s
}

@keyframes btn-anim3 {
  0% {
    right: -100%;
  }
  50%,100% {
    right: 100%;
  }
}

.login-box a span:nth-child(4) {
  bottom: -100%;
  left: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(360deg, transparent, #03e9f4);
  animation: btn-anim4 1s linear infinite;
  animation-delay: .75s
}

@keyframes btn-anim4 {
  0% {
    bottom: -100%;
  }
  50%,100% {
    bottom: 100%;
  }
}
    }}
  }
</style>
