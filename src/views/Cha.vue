<template>
    <div id="app">
         <el-row class="tac">
           <el-col :span="1"><div class="grid-content bg-purple">
            <Left></Left>
           </div>
         </el-col>
          <el-col :span="23"><div class="grid-content bg-purple">
            <div>
                <p><span class="rig" @click="flag1=1" v-if="flag1==0">切换站外</span>
                   <span class="rig" @click="flag1=0" v-if="flag1==1">切换站内</span>
                </p>
                <div v-if="flag1==0">
               <p><img src="../assets/img/sou.png"></p> 
             <p><input type="text" placeholder="搜企业,法人,产品,经营范围...">
              <button type="botton">搜索</button> </p>
              <br>
               <el-checkbox-group v-model="checkList">
                <el-checkbox label="全选"></el-checkbox>&nbsp;
                <el-checkbox label="文章"></el-checkbox>&nbsp;
                <el-checkbox label="日程"></el-checkbox>&nbsp;
                <el-checkbox label="合同"></el-checkbox>&nbsp;
                <el-checkbox label="任务"></el-checkbox>&nbsp;
                <el-checkbox label="动态"></el-checkbox>&nbsp;
                <el-checkbox label="销售跟单"></el-checkbox>
                <span class="you" @click="flag=1" v-if="flag==0"><a href="#"><i class="el-icon-search"></i>高级搜索</a></span>
                <span class="you" @click="flag=0" v-if="flag==1"><a href="#"><i class="el-icon-search"></i>收起</a></span>
                <p v-if="flag==1">
                <el-checkbox label="最近一周"></el-checkbox>&nbsp;
                <el-checkbox label="最近一月"></el-checkbox>&nbsp;
                </p>
            </el-checkbox-group> 
                </div>
              <div v-if="flag1==1">
                  <br><br><br><br><br><br><br><br>
                  <p><input type="text" placeholder="搜企业,法人,产品,经营范围...">
              <router-link tag="lo" to="/geren">
              <button type="botton">搜索</button></router-link> </p>
              <br>
               <el-checkbox-group v-model="checkList">
                <el-checkbox label="全选"></el-checkbox>&nbsp;
                <el-checkbox label="企业名"></el-checkbox>&nbsp;
                <el-checkbox label="法人/股东"></el-checkbox>&nbsp;
                <el-checkbox label="经营范围"></el-checkbox>&nbsp;
                <el-checkbox label="品牌/产品"></el-checkbox>&nbsp;
                
                <span class="you" @click="flag=1" v-if="flag==0"><a href="#"><i class="el-icon-search"></i>高级搜索</a></span>
                <span class="you" @click="flag=0" v-if="flag==1"><a href="#"><i class="el-icon-search"></i>收起</a></span>
                <div class="fla" v-if="flag==1">
                    <p><i class="el-icon-s-check"></i>&nbsp;&nbsp;基础条件</p>
                    <p>企业类型:<span class="blu1">不限</span><span class="blu2">有限责任公司</span>
                        <span class="blu2">股份有限公司</span><span class="blu2">国企</span><span class="blu2">独资公司</span>
                        <span class="blu2">外贸投资公司</span><span class="blu2">个体工商户</span>
                    </p>
                    <p>主营行业:<span class="blu1">不限</span><span class="blu2">金融业</span>
                        <span class="blu2">房地产</span><span class="blu2">建筑业</span><span class="blu2">制造业</span>
                        <span class="blu2">批发与零售业</span><span class="blu2">软件和信息技术服务业</span>
                    </p>
                     <p>注册资本:<span class="blu1">不限</span><span class="blu2">100万以内</span>
                        <span class="blu2">100-500万</span><span class="blu2">500-1000万</span><span class="blu2">1000-3000万</span>
                        <span class="blu2">3000-5000万</span><span class="blu2">5000万以上</span>
                    </p>
                     <p>注册区域:<span class="blu1">不限</span><span class="blu2">北京市</span>
                        <span class="blu2">上海市</span><span class="blu2">天津市</span><span class="blu2">重庆市</span>
                        <span class="blu2">广东省</span><span class="blu2">江苏省</span>
                    </p>
                     <p>联系方式:<span class="blu1">不限</span><span class="blu2">有电话</span>
                        <span class="blu2">无电话</span>
                    </p>
                </div>
            </el-checkbox-group> 
              </div>
               
            </div>
            </div>
         </el-col>
         </el-row>
    </div>
</template>
<script>
import Left from '../components/Left';

export default {
    name:'cha',
    data(){
        return{
            checkList:[],
            flag:0,
            flag1:1
        }
    },components:{
      Left,
    }

}
</script>
<style scoped>
    *{
        text-align: center;
        margin: 0 auto;
        padding: 0 0;
        font-size: 10px;    
    }
  .rig{margin-right: 100px;
      float: right;

  }
  input{
      width: 50%;
      border: 1px rgba(0, 168, 255, 1) solid;
      padding: 5px 0px;
  }
  button{
      padding: 4.75px 12px;
      color: white;
      background-color:rgba(0, 168, 255, 1);
      border: 0.5px rgba(0, 168, 255, 1) solid;
      border: none;
  }
  .you{
      margin-left: 60px;
  }
  .fla{
      margin-top: 20px;
      width: 53%;
      border: 0.5px black solid;
      padding-bottom: 50px;
      padding-top: 10px;
  }
  .fla p{
      text-align: left;
     margin: 15px 0;
     margin-left: 15px;
  }
  .blu1{
      margin: 0 5px;
      padding: 3px 7px;    
      background-color: rgba(0, 168, 255, 1);
      color: white;
      border-radius: 3px;
  }
   .blu2{
      margin: 0 5px;
      padding: 3px 7px;    
      border-radius: 3px;
  }
  .blu2:hover{
      background-color: rgba(0, 168, 255, 1);
      color: white;
  }
    .el-checkbox__label{
        padding-left: 1px !important;
        font-size: 10px !important;
    }
</style>