<template>
  <div id="app">
    <HeaderPage ref="HeaderPage"></HeaderPage>
    <nav class="header__nav" :class="{'red': state}">
        <ul class="header__nav-bar">
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
      state: false
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
    let nav = document.querySelector('.header__nav');
    window.addEventListener('scroll', () => {
      let header__nav = document.querySelector('.header__nav')
      if(header__nav.getBoundingClientRect().top < 20) this.state = true
      else this.state = false
      if(pageYOffset > 2200){
        let navCur = (nav.scrollWidth * (100 * (pageYOffset - 2200)) / (document.documentElement.scrollHeight-2200))/100 
        nav.scrollTo(navCur,0)
      }
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
  },
  watch: {
    state: function(){
      if(!window.matchMedia('(max-width: 450px)').matches){
        this.$refs.HeaderPage.changeState(this.state)
      }
    }
  }
};
</script>

<style lang="scss">

  .header__nav{
    z-index: 1;
    position: sticky;
    top: 0;
    background: #fff;
    overflow: auto;
    &.red{
      border-bottom: 1px solid $greyText;
    }
    &.red .nav-item{
        margin: 90px 0px 25px;
    }
  }
  .header__nav-bar{
    width: 1080px;
    padding: 0 10px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;

    .nav-item{
      margin: 50px 0px 25px;
      transition: all ease 0.2s;
      a{
        font-size: 16px;
        color: $greyText;
        &:hover{
          color: $mainColor; 
        }
      }
    }
  }

</style>
