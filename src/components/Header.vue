<template>
    <header class="header">
        <nav class="navbar wrapper">
            <div class="logo">
                <img src="../assets/Logo.png" alt="">
            </div>
            <ul class="menu">
                <li>
                    <img src="../assets/pin.svg" alt="">
                    Алматы
                </li>
                <li>О нас</li>
                <li>Аптеки</li>
                <li>Контакты</li>
            </ul>
            <div class="auth-info">
                <div class="item cabinet">
                    <img src="../assets/user.svg" alt="">
                    <p>Личный кабинет</p>
                </div>
                <div class="item lang">
                    <p>Ru </p>
                    <img src="../assets/Line.svg" alt="">
                </div>
            </div>
        </nav>

    </header>
</template>

<script>
    export default{
        name: 'Header'
    }
</script>

<style lang="scss" scoped>
.header{
    padding: 12px 0 7px;
    border-bottom: 1px solid #DEE0E4;
    .navbar{
        display: flex;
        align-items: center;

        .menu{
            margin-left: 60px;
            display: flex;
            align-items: center;
            li{
                margin-left: 50px;
                &:first-child{
                    display: flex;
                    align-items: center;
                    img{
                        margin-right: 10px;
                    }
                }
            }
        }

        .auth-info{
            margin-left: auto;
            display: flex;
            .item{
                margin-right: 20px;
                display: flex;
            }
            .cabinet{
                p{
                    color: #3BDE15;
                    margin-left: 8px;
                }
            }
            .lang{
                p{
                    margin-right: 8px;
                }
            }
        }
    }
}
</style>
