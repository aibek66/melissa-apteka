<template>
    <section class="search-nav">
        <nav class="nav wrapper">
            <div class="menu-box">
                <img src="../assets/menu.svg" alt="">
                <p>Каталог товаров</p>
            </div>
            <form action="">
                <input type="text" name="" id="" placeholder="Поиск лекарств">
                <img src="../assets/search.svg" alt="">
            </form>
            <div class="info">
                <div class="phone-box">
                    <img src="../assets/phone-icon.svg" alt="">
                    <div class="phone">
                        <p>+7 (727) 293 85 43</p>
                        <p>+7 (727) 291 08 88</p>
                    </div>
                </div>
                <div class="cart-box">
                    <img src="../assets/cart_circle.svg" alt="">
                </div>
            </div>
        </nav>
    </section>
</template>

<script>
export default {
    name: 'CatalogueSearchNav'
}
</script>

<style lang="scss" scoped>
    .search-nav{
        border-bottom: 1px solid #DEE0E4;
        padding: 24px 0;
        .nav{
            display: flex;
            justify-content: space-between;
            align-items: center;

            .menu-box{
                display: flex;
                align-items: center;
                margin-right: 60px;
                p{
                    margin-left: 15px;
                }
            }
            .info{
                display: flex;
                margin-left: 45px;
                .phone-box{
                    display: flex;
                    align-items: center;
                    margin-right: 40px;
                    .phone{
                        margin-left: 10px;
                        p{
                            font-size: 18px;
                        }
                    }
                }
            }
            form{
                flex: 1;
                position: relative;
                input{
                    width: 100%;
                    background: #FFFFFF;
                    border: 1px solid #DEE0E4;
                    border-radius: 100px;
                    font-size: 14px;
                    padding: 12px 28px;
                    &::placeholder{
                        color: #A1A4B2;
                        font-weight: 400;
                    }
                }
                img{
                    position: absolute;
                    right: 12px;
                    top: 50%;
                    transform: translateY(-50%);
                }
            }
        }
    }
</style>