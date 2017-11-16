<template>
<div class="tab">
   <div class="header">
        <img src="../../assets/food.jpg" alt="">
    </div>  
    <div>
        <ul>
            <li class="active">
                <router-link to="/">商品</router-link>
            </li>    
            <li>
                <router-link to="/ratings">评论</router-link>
            </li>    
            <li>
               <router-link to="/seller">商家</router-link>
            </li>    
        </ul>      
    </div>
   
</div>

  
</template>
<script>
export default {
  
}
</script>
<style>
.tab ul{
    /* overflow: hidden; */
}
.tab li{
    float: left;
    width: 33.33%;
    text-align:center;
    height: 2rem;
    line-height: 2rem;
    font-size: 1rem;
    border-bottom: 1px solid #4d555d;
    
}
.router-link-exact-active{
    color: #c00;
}
.header>img{
    width: 100%;
    height: 11rem;
}
</style>


