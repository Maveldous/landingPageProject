
<template>
  <section class="section">
      <div class="section__wrapper">
            <h3 class="section__wrapper-title">Где купить билет</h3>
            <img class="section__wrapper-img" src="../assets/images/thirdBlock__img.png" alt="Pic with ticket window">
            <p class="section__wrapper-textCircle window">
                <strong>На сайте </strong>
                <br>
            </p>
            <p class="section__wrapper-textCircle2">
                <a href="#">Здесь</a> можно найти билеты с любимыми числами и купить разом до 100 штук. А ещё доступна опция заказа пяти билетов, в которых будут все числа от 1 до 90.
            </p>
            <p class="section__wrapper-textCircle phone">
                <strong>В мобильном приложении </strong>
                <br>
            </p>
            <p class="section__wrapper-textCircle2">
                Удобно покупать билеты с <a class="textRef" href="#">iOS и Android </a>, следить за результатами розыгрышей и смотреть трансляции.
            </p>
            <p class="section__wrapper-textCircle store">
                <strong>В розничных точках продаж </strong>
                <br>
            </p>
            <p class="section__wrapper-textCircle2">
                На <a class="textRef" href="#">карте</a> можно найти киоски, лотерейные аппараты и партнёрские магазины: «Почта России», «Связной», «Билайн», «МегаФон», «Ростелеком», Tele2, «Перекрёсток», «Пятёрочка», «Бристоль».
            </p>
            <p class="section__wrapper-textCircle message">
                <strong>Через SMS </strong>
                <br>
            </p>
            <p class="section__wrapper-textCircle2">
                Нужно найти на специальной <a class="textRef" href="#">странице</a> идентификационный код лотереи и прислать его SMS-сообщением на номер 9999. Деньги спишутся с баланса мобильного телефона.
            </p>
            <p class="section__wrapper-textLineDouble"><strong>Продажи билетов на воскресный тираж закрываются в субботу в 17:20 по московскому времени.</strong></p>
      </div>
  </section>

</template>

<script>
export default {
  data: function(){
    return {

    }
  }
};
</script>

<style lang="scss">
    .section__wrapper-textCircle.window::after{
        background: url('../assets/images/thirdBlock__windowicon.png') center no-repeat ;
    }
    .section__wrapper-textCircle.phone::after{
        background: url('../assets/images/thirdBlock__phoneicon.png') center no-repeat ;
    }
    .section__wrapper-textCircle.store::after{
        background: url('../assets/images/thirdBlock__storeicon.png') center no-repeat ;
    }
    .section__wrapper-textCircle.message::after{
        background: url('../assets/images/thirdBlock__messageicon.png') center no-repeat ;
    }
    .section__wrapper-textLineDouble{
        padding: 22px 0 15px;
        position: relative;
        &::before{
            position: absolute;
            content: '';
            width: 50px;
            height: 0;
            top: 0;
            left: 0;
            border: 2px solid $mainColor;
        }
        &::after{
            position: absolute;
            content: '';
            width: 50px;
            height: 0;
            bottom: 0;
            left: 0;
            border: 1px solid $mainColor;
        }
    }

    
</style>