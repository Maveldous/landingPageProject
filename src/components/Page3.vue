
<template>
  <section class="section">
      <div class="section__wrapper">
            <h3 class="section__wrapper-title">Что можно выиграть</h3>
            <img class="section__wrapper-img" src="../assets/secondBlock__img.png" alt="Pic Man with checklist">
            <p class="section__wrapper-text">
                В первых турах можно выиграть от нескольких тысяч до нескольких миллионов рублей, а также автомобили, загородные дома и путешествия. Все выигрыши можно получить в денежном эквиваленте.
                <br><br>
                Самый крупный приз — джекпот. Это десятки и даже сотни миллионов рублей, он накапливается от тиража к тиражу. Джекпот можно выиграть, если 15 чисел верхнего или нижнего поля билета совпадут с номерами на первых 15 бочонках, вытянутых ведущим из мешка. Сумма рекордного джекпота в «Русском лото» уже больше 
                900 000 000 рублей.
            </p>
            <img class="section__wrapper-img" src="../assets/secondBlock__img2.png" alt="Pic Man with checklist">
            <p class="section__wrapper-text">
                Призовой фонд формируется из половины стоимости всех проданных билетов. 
                С начала 2019 года общая сумма выигрышей составила свыше 3 миллиардов рублей. Победителями стали около 2 миллионов участников лотереи.
            </p>
            <h5 class="section__wrapper-minorTitle">Самые крупные выигрыши в «Русском лото»</h5>
            <p class="section__wrapper-textCircle">
                <strong>Наталья Власова — 506 000 000 рублей.</strong>
                <br>
                1 204-й тираж, трансляция от 5 ноября 2017 года. Деньги пенсионерка решила потратить на покупку жилья, отдых, образование дочери и благотворительность.
            </p>
            <p class="section__wrapper-textCircle">
                <strong>Любовь и Сергей Догоровы — 500 000 000 рублей.</strong>
                <br>
                1 264-й тираж, трансляция от 1 января 2019 года. Победители вложились в путешествия, покупку квартиры, помощь родственникам и благотворительность. Часть суммы собираются инвестировать.
            </p>
            <p class="section__wrapper-textCircle">
                <strong>Николай и Оксана Мирошниченко — 500 000 000 рублей.</strong>
                <br>
                1 264-й тираж, трансляция от 1 января 2019 года. Полмиллиарда планируют потратить на путешествия, выплату ипотеки, помощь родственникам и благотворительность.
            </p>
            <p class="section__wrapper-text">
                В России все лотереи государственные и регулируются Федеральным законом № 138-ФЗ. Организаторами розыгрышей выступают Министерство спорта РФ и Министерство финансов РФ. Они утверждают условия лотерей и заключают контракты с операторами. Часть денег, вырученных от продажи билетов, идёт на финансирование государственных программ по развитию физической культуры и спорта.
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

    .section__wrapper-minorTitle{
        font-size: 30px;
        margin: 40px 0;
    }

    .section__wrapper-textCircle.animationStart::before, .section__wrapper-textCircle.animationStart::after{
        opacity: 1;
        transform: translateX(0);
    }

    .section__wrapper-textCircle{
        padding-left: 95px;
        position: relative;
        margin: 30px 0;
        &::before{
            transition: 2s ease all;
            opacity: 0;
            transform: translateX(-100px);
            position: absolute;
            content: '';
            left: 0;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            border: 2px solid #ED5E42;
        }
        &::after{
            transition: 2s ease all;
            opacity: 0;
            transform: translateX(-100px);
            position: absolute;
            content: '';
            left: 3px;
            top: 3px;
            width: 51px;
            height: 51px;
            border-radius: 50%;
            border: 1px solid #ED5E42;
        }
    }
</style>