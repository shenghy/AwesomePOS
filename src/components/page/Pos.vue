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
                             <li>
                                 <span>香辣鸡腿堡</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                              <li>
                                 <span>可口可乐</span>
                                 <span class="o-price">￥3元</span>
                             </li>
                             <li>
                                 <span>20元套餐A</span>
                                 <span class="o-price">￥20元</span>
                             </li>
                             <li>
                                 <span>超级外送全家桶</span>
                                 <span class="o-price">￥99元</span>
                             </li>
                             <li>
                                 <span>五味小吃桶</span>
                                 <span class="o-price">￥55元</span>
                             </li>
                             <li>
                                 <span>劲脆鸡腿堡土豆泥餐</span>
                                 <span class="o-price">￥39元</span>
                             </li>
                             <li>
                                 <span>劲脆鸡腿堡</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>香辣鸡腿堡土豆泥餐</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>伴鸡伴虾堡</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>吮指原味鸡套餐A</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>二块香辣鸡翅</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>黄金鸡块5块装</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>香甜粟米棒</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>芙蓉荟蔬汤</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>葡式蛋挞(经典)1只装</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>红豆派</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>圣代(草莓)</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>香辣鸡腿堡</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>圣代(巧克力)</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>香辣鸡腿堡</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             <li>
                                 <span>香辣鸡腿堡</span>
                                 <span class="o-price">￥15元</span>
                             </li>
                             

                         </ul>
                     </div>
                 </div>

                 <div class="goods-type">
                    
                     <el-tabs>
                           <el-tab-pane label="汉堡">
                               汉堡
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
export default {
  name: 'Pos',
  mounted:function(){
      var orderHeight=document.body.clientHeight;
      document.getElementById("order-list").style.height=orderHeight+'px';

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
        }]
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

</style>
