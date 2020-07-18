<template>
  <header class="header">
    <div class="header__main">
     <div class="mobileAddition"></div> 
      <article class="header__fixed" :class="{'red' : stateHeader}">
        <a href="#"><img src="../assets/images/header__logos-white.png" alt="header__logos-white" class="header__fixed-logo"></a>
        <ul class="header__fixed-networks">
          <li class="header__networks-item fb">
            <a @click="fbShare('URL','TITLE','IMG_PATH','DESC')"></a>
          </li>
          <li class="header__networks-item tw">
            <a @click="twShare('URL','TITLE')"></a>
          </li>
          <li class="header__networks-item vk">
            <a @click="vkShare('URL','TITLE','IMG_PATH','DESC')"></a>
          </li>
        </ul>
      </article>
      <div class="header__img">
        <img src="../assets/images/header__loto.png" alt="header__loto" class="header__img-inner">
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data: function(){
    return {
      stateHeader: false
    }
  },
  methods:{
    fbShare: function(purl, ptitle, pimg, text) {
      let url  = 'http://www.facebook.com/sharer.php?s=100';
      url += '&p[title]='     + encodeURIComponent(ptitle);
      url += '&p[summary]='   + encodeURIComponent(text);
      url += '&p[url]='       + encodeURIComponent(purl);
      url += '&p[images][0]=' + encodeURIComponent(pimg);
      this.popShare(url);
	  },
    twShare: function(purl, ptitle) {
      let url  = 'http://twitter.com/share?';
      url += 'text='      + encodeURIComponent(ptitle);
      url += '&url='      + encodeURIComponent(purl);
      url += '&counturl=' + encodeURIComponent(purl);
      this.popShare(url);
	  },
    vkShare: function(purl, ptitle, pimg, text) {
      let url  = 'http://vkontakte.ru/share.php?';
      url += 'url='          + encodeURIComponent(purl);
      url += '&title='       + encodeURIComponent(ptitle);
      url += '&description=' + encodeURIComponent(text);
      url += '&image='       + encodeURIComponent(pimg);
      url += '&noparse=true';
      this.popShare(url);
	  },
    popShare: function(url) {
		  window.open(url,'','toolbar=0,status=0,width=626,height=436');
    },
    changeState: function(value){
      this.stateHeader = value
    }
  },
  mounted: function(){
    if(window.matchMedia('(max-width: 450px)').matches){
      this.stateHeader = true
    }
  }
}
</script>

<style scoped lang="scss">
  
  .header__fixed{
    position: fixed;
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    margin-top: 44px;
    z-index: 2;
    transition: all 0.2s ease ;
    &.red{
      background: $mainColor;
      margin: 0;
      .header__networks-item{
        margin: 10px 10px 10px 0; 
        &.fb{
          background: url('../assets/images/header__fbhover-icon.png') center no-repeat;
        }
        &.tw{
          background: url('../assets/images/header__twhover-icon.png') center no-repeat;
        }
        &.vk{
          background: url('../assets/images/header__vkhover-icon.png') center no-repeat;
        }
      }
    }
  }
  
  .header__networks-item{
    display: inline-block;
    position: relative;
    width: 40px;
    height: 40px;
    margin-right: 10px;
    background: #fff;
    border: none;
    border-radius: 50%;
      a{
      display: block;
      width: 100%;
      height: 100%;
    }
  }

  .header__networks-item.fb{
      background: url('../assets/images/header__fb-icon.png') center no-repeat;
      &:hover{
        background: url('../assets/images/header__fbhover-icon.png') center no-repeat;
      }
  }


  .header__networks-item.tw{
      background: url('../assets/images/header__tw-icon.png') center no-repeat;
      &:hover{
        background: url('../assets/images/header__twhover-icon.png') center no-repeat;
      }
  }

  .header__networks-item.vk{
      background: url('../assets/images/header__vk-icon.png') center no-repeat;
      &:hover{
        background: url('../assets/images/header__vkhover-icon.png') center no-repeat;
      }
  }

  .header__img{
    display: flex;
    align-items: center;
    justify-content: center;
    max-width: 100%;
    height: auto;
    max-height: 640px;
    background: url('../assets/images/header__bg.png') no-repeat;
    background-size: cover;
    &-inner{
      margin: 12.5%;
      width: 39%;
      &:hover{
        animation: translatePoint 1s ease;
      }
    }
  }

  @keyframes translatePoint{
    0%{
        transform: translateX(10px);
    }
    12%{
        transform: translateX(-10px);
    }
    25%{
        transform: translateX(10px);
    }
    37%{
        transform: translateX(-10px);
    }
    50%{
        transform: translateX(10px);
    }
    62%{
        transform: translateX(-10px);
    }
    75%{
        transform: translateX(10px);
    }
    82%{
        transform: translateX(-10px);
    }
    100%{
        transform: translateX(10px);
    }
}

</style>
