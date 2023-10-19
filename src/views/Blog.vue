<script>
export default {
  data() {
    return {

    }
  }
}


</script>
<template>
  <RouterLink class=" customLink0 fs-1" to="/">ホームページ</RouterLink>
  <div class="BlogpPage">
    <div class="BlogTitle"><br>
      <h1 class="BlogTitle1">武弄組</h1>
      <h6 class="BlogTitle2">神式技研</h6>
    </div><br>
    <div class="BlogHeader">
      <div class="BlogHeaderLink">
        <RouterLink class="customLink1 " to="/">About</RouterLink>
        &nbsp; &nbsp;&nbsp; &nbsp;
        <RouterLink class="customLink1 " to="/">Archive</RouterLink>
      </div>
      <input type="text" placeholder="Search" class="BlogHeaderSearch">
    </div>
    <br><br>
    <div class="BlogContents">
      <div class="BlogLeft">
        <div class="BlogLeftTOP">

        </div>

        <div class="BlogLeftBetween">

        </div>
        <div class="BlogLeftDown">

        </div>
      </div>

      <div class="BlogBetween">
        <h2>Post</h2>

      </div>
      <div class="BlogRight">
        <h4>Categories</h4>
      </div>

    </div>
  </div>
</template>

<style lang="scss" scoped>
$mainColor1: white;

.customLink0 {
  text-decoration: none;
}

.customLink1 {
  text-decoration: none;
  font-size: 20pt;
  color: rgb(112, 112, 112);
}

.BlogpPage {
  margin: 0;
  background-color: rgb(243, 243, 243);
  width: 100vw;
  height: 500vh;

  .BlogTitle {
    .BlogTitle1 {
      font-size: 50pt;
    }

    .BlogTitle2 {
      font-size: 24pt;
      color: rgb(16, 95, 197);
    }
  }

  .BlogHeader {
    height: 10vh;
    background-color: rgb(255, 255, 255);
    display: flex;
    align-items: center;
    justify-content: space-around;

    .BlogHeaderLink {
      display: flex;
      justify-content: space-around;

    }

    .BlogHeaderSearch {
      border-radius: 10px;
      font-size: 16pt;
      width: 15vw;
      margin-left: 40vw;
    }
  }

  .BlogContents {

    display: flex;
    justify-content: space-between;
    border: 0px solid black;
    height: 500vh;
    margin: 100px;

    .BlogLeft {

      height: 200vh;
      width: 20vw;
      border: 0px solid black;

      .BlogLeftTOP {
        background-color: $mainColor1;
        height: 50vh;
        width: 340px;

      }

      .BlogLeftBetween {
        background-color: $mainColor1;
        height: 20vh;
        margin-top: 30px;
        width: 340px;
        border: 0px solid black;

      }

      .BlogLeftDown {
        margin-top: 30px;
        background-color: $mainColor1;
        height: 50vh;
        width: 340px;

      }


    }

    .BlogBetween {
      height: 500vh;
      width: 45vw;
      background-color: $mainColor1;
    }

    .BlogRight {
      height: 50vh;
      width: 20vw;
      border: 0px solid black;
    }



  }


}</style>