
<template>
  <section class="section">
      <div class="section__wrapper">
            <h3 class="section__wrapper-title">Как получить выигрыш</h3>
            <img class="section__wrapper-img" src="../assets/seventhBlock__img.png" alt="Pic with ticket window">
            <p class="section__wrapper-text">
                Чтобы получить выигрыш, нужно предъявить паспорт и лотерейный билет. Забрать приз можно в течение шести месяцев после обращения за выигрышем и подачей заявления.
                <br><br>
                Если в этот срок получить выигрыш по какой-то причине не удалось, нужно заполнить специальную форму, которая есть на сайте «Столото», и обратиться в лотерейный центр в Москве. 
                <br><br>
                В этом случае выигрыш будет ждать победителя ещё три года. Все выигрыши, за которыми никто не пришёл, перечисляются в государственный бюджет.
            </p>
            <h3 class="section__wrapper-minorTitle">Где забрать деньги</h3>
            <p class="section__wrapper-text">В зависимости от суммы есть несколько способов забрать приз:</p>
            <p class="section__wrapper-textCircle wallet">
                <strong>Перевести на баланс кошелька «Столото» — до 100 000 рублей </strong>
                <br>
                Этот вариант подойдёт, если вы указали номер телефона при покупке. Зарегистрируйтесь на сайте с этим номером и выберите «Перевести выигрыш в кошелёк» на странице информации о билете. Эти деньги можно использовать для покупки новых билетов.
            </p>
            <p class="section__wrapper-textCircle store">
                <strong>Забрать в точке продаж — до 2 000 рублей </strong>
                <br>
                Чтобы найти подходящую точку, нужно выбрать на странице с <a class="textRef" href="#">картой</a> «Столото» пункт «Получить выигрыш» и ввести сумму выигрыша.
            </p>
            <p class="section__wrapper-textCircle doc">
                <strong>Перевести на лицевой счёт — от 100 000 рублей </strong>
                <br>
                Для получения выигрыша нужно предоставить комплект документов и реквизиты счёта. Подробности — на <a class="textRef" href="#">сайте «Столото»</a>.
            </p>
            <p class="section__wrapper-textCircle coins">
                <strong>В лотерейном центре «Столото» в Москве можно получить <br> любую сумму. </strong>
            </p>
            <h3 class="section__wrapper-minorTitle">Какие налоги придётся заплатить</h3>
            <p class="section__wrapper-text bigline">
                Налог с выигрыша для россиян составляет 13%. Для нерезидентов РФ — 30%. Если за год вы выиграли не больше 4 000 рублей, ничего платить не нужно.
                <br>
                <br>
                Выплату от 15 000 рублей вы получите уже с удержанным налогом 13%. Если выигрыш меньше 15 000 рублей, нужно подать в налоговый орган по месту жительства декларацию, оформленную по форме 3-НДФЛ, а потом заплатить налог в банке или онлайн. То же самое придётся сделать для получения вещевого приза: например, автомобиля или квартиры. 
                <br>
                <br>
                Каждый выигрыш фиксируется в системе Федеральной налоговой службы. Все невостребованные выигрыши перечисляются в госбюджет, так как организатор лотерей — государство.
            </p>

      </div>
  </section>

</template>

<script>
export default {
  data: function(){
    return {

    }
  },
  props: {
    
  }
};
</script>

<style lang="scss">
    .section__wrapper-textCircle.wallet::after{
        background: url('../assets/seventhBlock__walleticon.png') center no-repeat ;
    }
    .section__wrapper-textCircle.doc::after{
        background: url('../assets/seventhBlock__docicon.png') center no-repeat ;
    }
    .section__wrapper-textCircle.coins::after{
        background: url('../assets/seventhBlock__coinsicon.png') center no-repeat ;
    }
    .section__wrapper-text.bigline{
        position: relative;
        padding-bottom: 150px;
        &::after{
            position: absolute;
            content: '';
            bottom: 0;
            right: 50%;
            transform: translateX(50%);
            width: 100%;
            height: 50px;
            background: #ED5E42;
        }
    }

    
</style>