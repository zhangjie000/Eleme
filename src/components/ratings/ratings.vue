<template>
<div class="comment">
    <div class="serverTime">
        <div class="serverScore">
            <p>4.2</p>
            <p>综合评分</p>
            <p>高于周边商家68.2%</p>
        </div>
        <div class="serverAttitude">
            <p>
                <span>服务态度</span>
                <span>★★★★☆</span>
                <span>4.1</span>
            </p>
            <p>
               <span>商品评分</span>
                <span>★★★★☆</span>
                <span>4.3</span>
            </p>
            <p>
                <span >送达时间</span>
                <span class="delivery">38分钟</span>
            </p>

        </div>
        
    </div>
    <div class="selectInfo">
       <ul>
           <li>
               <span>全部</span>
               <span class="number">24</span>
           </li>
           <li>
               <span>满意</span>
               <span class="number">16</span>
           </li>
           <li>
               <span>不满意</span>
               <span class="number">9</span>
           </li>
       </ul>
       <p class="onlyContent"> <span></span>只看有内容的评论</p>
    </div>
    <div clsss="commentConent">

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

        }
    }
  
}
</script>
<style scoped>
html,body{
    overflow: hidden;
    height: 100%;
}

.comment{
    height: calc(100% - 13rem);
    margin-top: 2rem;
   
}
.serverTime{
   
    padding: 0.5rem 0px;
     border-bottom:1px solid #dedede;
    overflow: hidden;
}
.serverScore{
    width: 40%;
    border-right:1px solid #dedede;
    float: left;
    text-align: center;
}
.serverScore p:first-child{
    font-size: 1.5rem;
    color: #c00;
}
.serverScore p:nth-child(2){
    font-size: 0.8rem;
}
.serverScore p:nth-child(3){
    font-size: 0.8rem;
    color: #aaa;
}

.serverAttitude{
    width: 60%;
    float: left;
    padding-left: 1rem;
    line-height: 1.3rem;
}
.serverAttitude>p{
     font-size: 0.8rem;
}
.serverAttitude>p span:nth-child(2){
    color: #c00;
    margin:0 0.5rem;
}
.serverAttitude>p span:nth-child(3){
     color: #c00;
}

.serverAttitude>p span.delivery{
    color: #aaa;
}
.serverAttitude>p span.number{
    font-size: 0.7rem;
}
.selectInfo{
    margin-top: 1rem;
    border-top: 1px solid #dedede;
    border-bottom: 1px solid #dedede;
    padding: 1.5rem 1rem;
}
.selectInfo ul>li{
    display: inline-block;
    width: 4.5rem;
    line-height: 1.8rem;
    text-align: center;
    font-size: 0.9rem;
}
.selectInfo ul>li:nth-child(1){
    /* background-color: #00a9dc; */
    background-color: rgba(0,160,220,.2);
    color: #4d555f;
}
.selectInfo ul>li:nth-child(2){
     background-color: rgba(0,160,220,.2);
    color: #4d555f;
    margin: 0px 0.5rem
}
.selectInfo ul>li:nth-child(3){
     background-color:rgba(77,85,93,.2);
    color: #4d555f;
}
.onlyContent{
    padding-top: 1rem;
}
</style>


