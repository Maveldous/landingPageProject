<template>
  <div id="app">
    <HeaderPage :content="state"></HeaderPage>
    <nav class="header__nav" :class="{'red': state}">
        <div class="burgerBtn" @click="btnActive = !btnActive" :class="{'change':btnActive}">
          <div class="bar1"></div>
          <div class="bar2"></div>
          <div class="bar3"></div>
        </div>
        <ul class="header__nav-bar" v-show="btnActive">
          <li class="nav-item">
            <a href="#">Что можно выиграть</a>
          </li>
          <li class="nav-item">
            <a href="#">Где купить билет</a>
          </li>
          <li class="nav-item">
            <a href="#">Как играть</a>
          </li>
          <li class="nav-item">
            <a href="#">Туры лотереи</a>
          </li>
          <li class="nav-item">
            <a href="#">Где узнать результаты</a>
          </li>
          <li class="nav-item">
            <a href="#">Как получить выигрыш</a>
          </li>
        </ul>
    </nav>
    <Page2></Page2>
    <Page3></Page3>
    <Page4></Page4>
    <Page5></Page5>
    <Page6></Page6>
    <Page7></Page7>
    <Page8></Page8>
    <FooterPage></FooterPage>
  </div>
</template>

<script>
import HeaderPage from "./components/HeaderPage.vue";
import Page2 from "./components/Page2.vue";
import Page3 from "./components/Page3.vue";
import Page4 from "./components/Page4.vue";
import Page5 from "./components/Page5.vue";
import Page6 from "./components/Page6.vue";
import Page7 from "./components/Page7.vue";
import Page8 from "./components/Page8.vue";
import FooterPage from "./components/FooterPage.vue";


export default {
  name: "App",
  data: function(){
    return {
      state: false,
      btnActive: true
    }
  },
  components: {
    HeaderPage,
    Page2,
    Page3,
    Page4,
    Page5,
    Page6,
    Page7,
    Page8,
    FooterPage
  },
  mounted: function () {
    window.addEventListener('scroll', () => {
      let header__nav = document.querySelector('.header__nav')
      if(header__nav.getBoundingClientRect().top < 20) this.state = true;
      else this.state = false;
    })

    const circle = document.querySelectorAll('.section__wrapper-textCircle')
    const options = {
        root : null,
        rootMargin: '0px',
        threshold: 0.1
    }
    let handleNew = function(circleOne){
        circleOne.forEach( circleItem => {
            if(circleItem.intersectionRatio > 0){
                circleItem.target.className += " animationStart";
            }
        })
    }.bind(this)
    const observer = new IntersectionObserver(handleNew, options)

    circle.forEach(item => {
        observer.observe(item)
    })
  }
};
</script>

<style lang="scss">
  
  @media ( max-width: 900px ) {
    nav.header__nav.red .burgerBtn{
      margin: 63px 10px 0;
    }
    nav .burgerBtn{
      display: inline-block;
      position: relative;
    }
    .header__nav .header__nav-bar{
      position: absolute;
      z-index: 3;
      background: #fff;
      display: block;
    }
    .header__nav.red .header__nav-bar .nav-item, .header__nav .header__nav-bar .nav-item{
        margin: 5px 0;
        border-bottom: 1px solid #333;
    }
  }

  @media ( max-width: 480px ) {
    body section{
      font-size: 16px;
    }
    .section__wrapper-titleMain{
      font-size: 27px;
    }
    .section__wrapper-strongText{
      font-size: 18px;
    }
    .section__wrapper-textLine, .section__wrapper-textLineAdd{
      padding-left: 15px;
    }
    .section__wrapper{
      padding: 0 15px;
    }
    .section__wrapper-textCircle{
      padding-left: 45px;
    }
    .section__wrapper-textCircle::before{
      width: 35px;
      height: 35px;
    }
    .section__wrapper-textCircle::after{
      width: 31px;
      height: 31px;
    }
    .header__main .header__fixed{
      margin-top: 20px;
    }
    .header__fixed-networks .header__networks-item{
      width: 25px;
      height: 25px;
    }
    .header__fixed-logo{
      width: 113px;
    }
  }

  @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

  h1,h2,h3,h4,h5,h6,p,li,ul{
    list-style: none;
    padding: 0;
    margin: 0;
  }

  a{
    text-decoration: none;
  }

  body{
    font-family: Roboto;
    font-size: 18px;
    padding: 0;
    margin: 0;
  }

  .section__wrapper{
    max-width: 740px;
    margin: 50px auto;
  }

  .textRef{
    color: #3670F9;
    border-bottom: 1px solid #3670F9;
    &:visited{
      color: #9197A3;
      border-bottom: 1px solid #9197A3;
    }
    &:hover{
      color: #ED5E42;
      border-bottom: 1px solid #ED5E42;
    }
  }

  .header__nav{
    z-index: 1;
    position: sticky;
    top: 0;
    background: #fff;
    &.red .nav-item{
        margin: 70px 0px 25px;
    }
  }
  .header__nav-bar{
    max-width: 1080px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;

    .nav-item{
      margin: 50px 0px 25px;
      a{
        font-size: 16px;
        color: #919DA3;
        &:hover{
          color: #ED5E42; 
        }
      }
    }
  }

.burgerBtn {
  display: none;
  cursor: pointer;
  margin: 10px 10px 0;
}
.header__nav.red .burgerBtn{
  margin: 80px 10px 0;
}

.bar1, .bar2, .bar3 {
  width: 35px;
  height: 5px;
  background-color: #333;
  margin: 6px 0;
  transition: 0.4s;
}

.change .bar1 {
  -webkit-transform: rotate(-45deg) translate(-9px, 6px) ;
  transform: rotate(-45deg) translate(-9px, 6px) ;
}

.change .bar2 {
  opacity: 0;
}

.change .bar3 {
  -webkit-transform: rotate(45deg) translate(-8px, -8px) ;
  transform: rotate(45deg) translate(-8px, -8px) ;
}

</style>
