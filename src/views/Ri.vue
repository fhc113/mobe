<template>
  <div class="about">
    <!-- <Header></Header> -->
    <el-row class="tac">
          <el-col :span="1"><div class="grid-content bg-purple">
            <Left></Left>
           </div>
         </el-col>
        <el-col :span="16"><div class="grid-content bg-purple">
         
           <br>
            <div class="blu">
         <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
                      <!-- <i class="el-icon-printer" style="margin-top:8px;margin-left:5px;"></i>&nbsp;&nbsp; -->
                    <el-submenu index="2">
                      &nbsp;&nbsp;
    <template slot="title">&nbsp;&nbsp;&nbsp;&nbsp;我的日程</template>
    <el-submenu index="2-1">
      <template slot="title">常用检索</template>
      <div>
        <p class="p1">我的日程</p>
        <p class="p1">团队日程</p>
        <p class="p1">抄送给我的日程</p>
      </div>
    </el-submenu>
    <el-submenu index="2-2">
      <template slot="title">自定义条件</template>
     <img src="../assets/img/nei.png" width="100%" class="saq">
    </el-submenu>
  </el-submenu>
      <span class="yuan">日程总数<br><strong>26</strong></span>
      <span class="yuan">未完成<br><strong>12</strong></span>
      <span class="yuan">延期<br><strong>5</strong></span>
      <input type="text" placeholder="日程，创建人...">
   </el-menu>
          </div>
           <div class="bluxia">
             <p class="xing"><span>&nbsp;&nbsp;&nbsp;2019-03-05第二周</span>
             <span class="shijian">
          <el-radio-group v-model="tabPosition">
              <el-radio-button label="zi" class="daxiao">自定义</el-radio-button>
              <el-radio-button label="ri" class="daxiao">日</el-radio-button>
              <el-radio-button label="zhou" class="daxiao">周</el-radio-button>
              <el-radio-button label="yue" class="daxiao">月</el-radio-button>
           </el-radio-group>
             </span>
             
             </p>
           </div>
              <img src="../assets/img/zhuang.png" width="95%" class="swsw">
              <img src="../assets/img/zhuang.png" width="95%" class="swsw">
              <img src="../assets/img/zhuang.png" width="95%" class="swsw">
              <div class="bluxia">
               &nbsp;&nbsp;&nbsp; 日总结
              </div>
              <div class="as">
                今日还未写日总结 &nbsp;&nbsp; <a href="#">（写总结）</a>
              </div>
          </div></el-col>
        <el-col :span="7"><div class="grid-content bg-purple">
          <img src="../assets/img/zhuang1.png" width="75%" class="swsw">
          </div></el-col>
    </el-row>
  </div>
</template>
<script>
import Left from '../components/Left';
export default {
  name:'ri',
  data(){
    return{
      tabPosition:'ri'
    }
  },components:{
      Left,
    }
   
}
</script>
<style scoped>
    *{
      margin:  0 auto;
      padding: 0 0;
    }
    .blu{
       border-bottom: cyan 1.5px solid;
   }
  input{
      width: 20%;
      border: 0.5px rgba(0, 168, 255, 1) solid;
      float: right;
  }
   ::v-deep .el-menu--horizontal>.el-submenu .el-submenu__title{
    height: 22px;
     line-height: normal;
    
   }
   /* .saq{
     padding: 5px 10px;
   } */
   .p1{
     margin: 3px 0;
     padding: 3px 0;
     font-size: 10px;
     margin-left: 10px;
   }
   .p1:hover{
     cursor: pointer;
     background-color: rgba(242, 242, 242, 1);
   }
   .swsw{
     margin-top: 10px;
     margin-left: 18px;
   }
   .yuan{
     margin: 0 5px;
     padding: 2px 0;
     width: 50px;
     background-color: aliceblue;
     border: 0.5px darkgray solid;
     display: inline-block;
     border-radius: 5px;
     font-size: 10px;
     text-align: center;
   }
   ::v-deep .el-radio-button__inner{
    padding: 2px 5px;
    border-radius: 0px;
    font-size: 12px;
    
}
  .shijian{
    float: right;
    margin-right: 20px;
  }
   .erqi{
      
      height: 500px;
   }
   .bluxia{
     width: 95%;
     margin-top: 10px;
     border: 0.5px darkgray solid;
     padding: 10px 0;
     font-size: 12px;
     color: darkgray;
   }
  
   .as{
         width: 95%;
         font-size: 10px;
         padding: 20px 0;
         margin-top: 10px;
         background-color: rgba(242, 242, 242, 1);
         text-align: center;
   }
</style>
