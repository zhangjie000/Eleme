<template>
<div class="goods">
    <div class="menu-sidebar">
        <ul>
            <li v-for="item in goods">{{ item.name }}</li>
        </ul>
    </div>
    <div class="menu-details">
        <ul>
            <li v-for="item in goods">
                <h3 class="menu-details-title">{{item.name}}</h3>
                <div>
                    <ul>
                        <li class="foodsList" v-for="food in item.foods">
                            <div class="icon" >
                                <img :src="food.icon"  width="57" height="57" alt="">
                            </div>
                            <div class="goods-details"> 
                                <h4 class="goods-name">{{food.name}}</h4>
                                 <p class="goods-description">{{food.description}}</p>
                                 <p class="goods-sellCount"><span>月销{{food.sellCount}}份</span><span>好评率{{food.rating}}%</span></p>
                                 <p class="goods-price">￥{{food.price}}</p>
                            </div>
                        </li>
                    </ul>
                  
                  
                    
                </div>
                <div></div>
            </li>
        </ul>
        
    </div>
    
     
     
</div>
  
</template>
<script>
import axios from 'axios'
export default {
    created(){
        axios.get('static/data.json').then((res) => {
            this.goods=res.data.goods
            console.log(res)
        })
    },
    data(){
        return {
            goods:[],
        }
    }
  
}
</script>
<style scpoed>
html,body{
    overflow: hidden;
    height: 100%;
}
.goods{
    height: calc(100% - 13rem);
}
.menu-details,.menu-details ul{
  height: 100%;
}
.menu-sidebar {
   display: inline-block;
   height: 100%;
   background-color: #ededed;
}
.menu-sidebar ul li{
    width: 5rem;
    padding: 0.6rem 0.4rem;
    background-color: #ededed;
    
}
.menu-sidebar ul{
    float: left;
   
}
.menu-details{
    float: right;
    width: calc(100% - 5rem);
    overflow: hidden;
   
}
.menu-details ul {
    height: 100%;
     overflow: auto;
    
}

.menu-details .menu-details-title{
    background: #ededed;
    height: 2rem;
    line-height: 2rem;
    border-left:2px solid #aaa;
    padding-left: 1rem;
}

    
 .menu-details .icon{
     display: inline-block;
      vertical-align:middle;
      padding: 0 1rem;
}

 .foodsList{
     border-bottom: 1px solid #aaa;
     padding: 0.5rem 0px;
 }
.menu-details .goods-details{
    display: inline-block;
     vertical-align:middle;
}
.goods-details .goods-name{
    font-size:1rem;
}
.goods-details .goods-description{
    font-size:0.5rem;
    color: #aaa;
}
.goods-details .goods-sellCount :first-child{
   font-size:0.5rem;
    color: #aaa;
    margin-right: 1rem;
}
.goods-details .goods-sellCount :last-child{
   font-size:0.5rem;
    color: #aaa;
}
.goods-details .goods-price{
    font-size:1rem;
    color: #c00;
}
</style>


