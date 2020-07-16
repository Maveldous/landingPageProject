<template>
  <header class="header">
    <div class="header__main">
      <article class="header__fixed" :class="{'red' : content}">
        <a href="#"><img src="../assets/header__logos-white.png" alt="header__logos-white" class="header__fixed-logo"></a>
        <ul class="header__fixed-networks">
          <li class="header__networks-item fb">
            <a href="#"></a>
          </li>
          <li class="header__networks-item tw">
            <a href="#"></a>
          </li>
          <li class="header__networks-item vk">
            <a href="#"></a>
          </li>
        </ul>
      </article>
      <div class="header__img">
        <img src="../assets/header__loto.png" alt="header__loto" class="header__img-inner">
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data: function(){
    return {
      
    }
  },
  props: ['content']
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
      background: #ED5E42;
      margin: 0;
      .header__networks-item{
        margin: 10px 10px 10px 0; 
      }
    }
  }

  .header__networks-item{
    display: inline-block;
    width: 40px;
    height: 40px;
    margin-right: 10px;
    background: #fff;
    border: none;
    border-radius: 50%;
  }

  .header__networks-item{
    a{
      display: block;
      width: 100%;
      height: 100%;
    }
  }

  .header__networks-item.fb{
      background: url('../assets/header__fb-icon.png') center no-repeat;
      &:hover{
        background: url('../assets/header__fbhover-icon.png') center no-repeat;
      }
  }

  .header__networks-item.tw{
      background: url('../assets/header__tw-icon.png') center no-repeat;
      &:hover{
        background: url('../assets/header__twhover-icon.png') center no-repeat;
      }
  }

  .header__networks-item.vk{
      background: url('../assets/header__vk-icon.png') center no-repeat;
      &:hover{
        background: url('../assets/header__vkhover-icon.png') center no-repeat;
      }
  }

  .header__img{
    display: flex;
    align-items: center;
    justify-content: center;
    max-width: 100%;
    height: auto;
    max-height: 640px;
    background: url('../assets/header__bg.png') no-repeat;
    background-size: cover;
    .header__img-inner{
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
