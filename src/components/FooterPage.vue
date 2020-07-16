<template>
    <footer class="footer">
        <p class="footer__title">© 2019 Лайфхакер</p>
    </footer>
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
    .footer{
        width: 100%;
        display: flex;
        justify-content: flex-end;
        align-items: center;
        margin-top: 95px;
        background: #000;
        .footer__title{
            margin: 20px 50px;
            font-size: 16px;
            color: #fff;
        }
    }

    
</style>