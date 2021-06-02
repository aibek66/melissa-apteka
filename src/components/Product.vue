<template>
    <div class="item">
        <img class="like-icon" src="../assets/like.svg" alt="">
        <div class="img-box">
            <img src="../assets/img1.png" alt="">
        </div>
        <div class="name">
            <p>{{item.name}}</p>
        </div>
        <div class="price">
            <h3>{{item.price}}</h3>
        </div>
        <div class="btn">
            <button>
                <img src="../assets/Cart.svg" alt="">
                <span>В корзину</span>
            </button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Product',
    props: {
        item: {}
    }
}
</script>

<style lang="scss" scoped>
.item{
    width: 100%;
    border: 1px solid #DEE0E4;
    background: #FFFFFF;
    border-radius: 6px;
    padding: 30px 20px;

    display: flex;
    flex-direction: column;
    align-items: center;
    font-size: 16px;
    text-align: center;
    position: relative;

    .like-icon{
        position: absolute;
        right: 15px;
        top: 20px;
    }

    h3{
        font-size: 18px;
        margin: 12px 0;
    }

    button{
        width: 150px;
        background-color: #fff;
        border: 1.4px solid #05054B;
        border-radius: 20px;
        padding: 9px 0;
        cursor: pointer;

        display: flex;
        align-items: center;
        justify-content: center;
        span{
            font-size: 14px;
            font-weight: 600;
            color:  #05054B;
            margin-left: 10px;
        }
    }
}
</style>