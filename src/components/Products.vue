
<template>
    <section class="wrapper">
        <h1>{{sectionTitle.name}}</h1>
        <div class="container">
            <div class="filter-box">
                <ul class="item category">
                    <li v-for="(el,index) in categories" :key="index" @click="filterData(el, index)" :class="[sectionTitle.name==el.name && 'active']">
                        {{el.name}}
                        <img src="../assets/Line2.svg" alt="">
                    </li>
                </ul>
                <div class="item">
                    <input type="range" min="0" max="180" step="20" value="10,180" />
                </div>
                <div class="item">
                    <div class="checkbox-el">
                        <input v-model="checked.stock" @click="filterDataByCheckbox(stock)" type="checkbox" name="checkbox" id="">
                        <label for="checkbox">В наличии</label>
                    </div>
                    <div class="checkbox-el">
                        <input v-model="checked.sale" @click="filterDataByCheckbox(sale)" type="checkbox" name="" id="">
                        <span>Акционные товары</span>
                    </div>
                </div>
            </div>
            <div class="products">
                <Product v-for="(el,index) in products" :key="index" :item="el">
                </Product>
            </div>
        </div>
    </section>
</template>

<script>
import Product from './Product.vue';
import items from '../data.json';

export default {
    name: 'Products',
    components:{
        Product
    },
    data(){
        return{
            products: items.products,
            categories: items.categories,
            sectionTitle: {
                name: items.categories[0].name,
                category: items.categories[0].category
            },
            checked: {
                stock: false,
                sale: false
            },

        }
    },
    methods:{
        filterData(el){
            this.products = items.products.filter(obj=> obj.category == el.category && (obj.stock == this.checked.stock || obj.sale == this.checked.sale));
            this.changeSectionTitle(el);

        },
        changeSectionTitle(el){
            this.sectionTitle.name = el.name;
            this.sectionTitle.category = el.category
        },
        filterDataByCheckbox(index){
            this.checked[index] = !this.checked[index];
            this.products = items.products.filter(el=>(el.stock == this.checked.stock) &&  (el.sale == this.checked.sale || el.category == this.sectionTitle.category))
            
        }
    },
    mounted(){
        this.filterData(this.sectionTitle);
    }
}
</script>

<style lang="scss" scoped>
.container{
    display: flex;

    .filter-box{
        width: 25%;
        margin-right: 20px;
        .item{
            border: 1px solid #DEE0E4;
            border-radius: 6px;
            padding: 20px 16px;
            margin-bottom: 25px;
            li{
                margin-bottom: 17px;
                cursor: pointer;
                display: flex;
                justify-content: space-between;
                &:last-child{
                    margin-bottom: 0;
                }
                &.active{
                    color: #3BDE15;
                }
            }
            .checkbox-el{
                input[type="checkbox"]{
                    // position: absolute;
                    // opacity: 0;
                    &+label{
                        position: relative;
                    }
                    & + label:before {
                        content: '';
                        margin-right: 10px;
                        display: inline-block;
                        vertical-align: text-top;
                        width: 16px;
                        height: 16px;
                        border: 1px solid #A1A4B2;
                        background: white;
                        border-radius: 2px;
                    }
                }
            }
        }
    }
}
h1{
    font-size: 28px;
    margin: 40px 0 25px;
}
.products{
    width: 75%;
    display: grid;
    grid-template-columns: repeat(4,1fr);
    grid-gap: 20px;
    align-items: flex-start;
}
</style>