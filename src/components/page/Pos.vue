<template>
  <div class="pos">
    <div>
        <el-row >
            <el-col :span="7" class="pos-order" id="order-list">

            <el-tabs>
                <el-tab-pane label="点餐">
                    <el-table :data="tableData" border show-summary style="width: 100%" >
                    
                        <el-table-column prop="goodsName" label="商品"  ></el-table-column>
                        <el-table-column prop="count" label="量" width="50"></el-table-column>
                        <el-table-column prop="price" label="金额" width="70"></el-table-column>
                        <el-table-column  label="操作" width="100" fixed="right">
                            <template scope="scope">
                                <el-button type="text" size="small">删除</el-button>
                                <el-button type="text" size="small">增加</el-button>

                            </template>
                        </el-table-column>
                    </el-table>
                        <div class="order-btn">
                            
                                <el-button type="warning" >挂单</el-button>
                                <el-button type="danger" >删除</el-button>
                                <el-button type="success" >结账</el-button>
                            
                        </div>
                </el-tab-pane>

                <el-tab-pane label="挂单">
                    挂单
                </el-tab-pane>
                 <el-tab-pane label="外卖">
                   外卖
                </el-tab-pane>



            </el-tabs>



            </el-col>


             <!--商品展示-->
            <el-col :span="17">
                <div class="often-goods">
                    <div class="title">常用商品</div>
                    <div class="often-goods-list">

                        <ul>
                            <li v-for="goods in oftenGoods">
                                <span>{{goods.goodsName}}</span>
                                <span class="o-price">￥{{goods.price}}元</span>
                            </li>

                        </ul>
                    </div>
                </div>

<div class="goods-type">

    <el-tabs>
        <el-tab-pane label="汉堡">
<ul class='cookList'>
   

<li v-for="goods in type0Goods">
    <span class="foodImg"><img :src="goods.goodsImg" width="100%"></span>
    <span class="foodName">{{goods.goodsName}}</span>
    <span class="foodPrice">￥{{goods.price}}元</span>
</li>


               
            </ul>
        </el-tab-pane>
            <el-tab-pane label="小食">
            小食
        </el-tab-pane>
        <el-tab-pane label="饮料">
            饮料
        </el-tab-pane>
        <el-tab-pane label="套餐">
            套餐
        </el-tab-pane>

    </el-tabs>
</div>

            </el-col>
        </el-row>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Pos',
  mounted:function(){
      var orderHeight=document.body.clientHeight;
      document.getElementById("order-list").style.height=orderHeight+'px';
  },
  created(){
      axios.get('http://jspang.com/DemoApi/oftenGoods.php')
      .then(response=>{
         console.log(response);
         this.oftenGoods=response.data;
      })
      .catch(error=>{
          console.log(error);
          alert('网络错误，不能访问');
      })
  },
  data () {
    return {
      tableData: [{
          
          goodsName: '可口可乐',
          price: 8,
          count:1
        }, {
          
          goodsName: '香辣鸡腿堡',
          price: 15,
          count:1
        }, {
         
          goodsName: '爱心薯条',
          price: 8,
          count:1
        }, {
         
          goodsName: '甜筒',
          price: 8,
          count:1
        }],
      oftenGoods:[],
       type0Goods:[
          {
              goodsId:1,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'香辣鸡腿堡',
              price:18
          }, {
              goodsId:2,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'田园鸡腿堡',
              price:15
          }, {
              goodsId:3,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'和风汉堡',
              price:15
          }, {
              goodsId:4,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'快乐全家桶',
              price:80
          }, {
              goodsId:5,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'脆皮炸鸡腿',
              price:10
          }, {
              goodsId:6,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'魔法鸡块',
              price:20
          }, {
              goodsId:7,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'可乐大杯',
              price:10
          }, {
              goodsId:8,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'雪顶咖啡',
              price:18
          }, {
              goodsId:9,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'大块鸡米花',
              price:15
          }, {
              goodsId:20,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'香脆鸡柳',
              price:17
          }
          
      ],
     
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
   .pos{
       font-size: 12px;
   }
   .pos-order{
      
       background-color: #F9FAFC;
       border-right:1px solid #C0CCDA;
   }
   .order-btn{
     margin-top:10px;
     text-align: center;
   }
   .title{
       height: 20px;
       border-bottom:1px solid #D3DCE6;
       background-color: #F9FAFC;
       padding:10px;
   }
   .often-goods-list ul li{
      list-style: none;
      float:left;
      border:1px solid #E5E9F2;
      padding:10px;
      margin:5px;
      background-color:#fff;
   }
   .goods-type{
       clear:both;
   }
   .o-price{
      color:#58B7FF; 
   }
   .often-goods-list{
       border-bottom:1px solid #C0CCDA;
       height:auto;
       overflow: hidden;
       padding-bottom:10px;
       background-color:#F9FAFC;
   }

   .cookList li{
       list-style: none;
       width:23%;
       border:1px solid #E5E9F2;
       height: auot;
       overflow: hidden;
       background-color:#fff;
       padding: 2px;
       float:left;
       margin: 2px;

   }
   .cookList li span{
       
        display: block;
        float:left;
   }
   .foodImg{
       width: 40%;
   }
   .foodName{
       font-size: 18px;
       padding-left: 10px;
       color:brown;

   }
   .foodPrice{
       font-size: 16px;
       padding-left: 10px;
       padding-top:10px;
   }

</style>
