<template>
    <div id="app">
       <el-row class="tac">
         <el-col :span="1"><div class="grid-content bg-purple">
            <Left></Left>
           </div>
         </el-col>
         <el-col :span="23"><div class="grid-content bg-purple">
           <div class="blu">
         <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
                      <!-- <i class="el-icon-printer" style="margin-top:8px;margin-left:5px;"></i>&nbsp;&nbsp; -->
                    <el-submenu index="2">
    <template slot="title">我的日程</template>
    <el-submenu index="2-1">
      <template slot="title">常用检索</template>
      <div>
        <p class="p1">我的任务</p>
        <p class="p1">团队任务</p>
        <p class="p1">公司任务</p>
      </div>
    </el-submenu>
    <el-submenu index="2-2">
      <template slot="title">自定义条件</template>
     <img src="../assets/img/nei.png" width="100%" class="saq">
    </el-submenu>
  </el-submenu>
      <span class="yuan"> <p>本月任务 <br><strong>￥52000元</strong></p> <p>已完成 <br><strong class="red">￥12000元</strong></p></span>
      <span class="yuan"> <p>本年任务 <br><strong>￥92000元</strong></p> <p>已完成 <br><strong class="red">￥52000元</strong></p></span>
      <span class="yuan"> <p>团队任务 <br><strong>￥99999元</strong></p> <p>已完成 <br><strong class="red">￥72000元</strong></p></span>
      <span class="rig">快速创建任务</span>
   </el-menu>
          </div>
          <el-table
    :data="tableData"
    style="width: 100%">
    <el-table-column
      prop="date"
      label="年度"
      width="150">
    </el-table-column>
      <el-table-column
        prop="name"
        label="任务类型"
        width="120">
      </el-table-column>
    
        <el-table-column
          prop="province"
          label="任务对象"
          width="120">
        </el-table-column>
        <el-table-column
          prop="city"
          label="全年任务目标"
          width="120">
        </el-table-column>
          <el-table-column label="一月">
        <el-table-column
          prop="address"
          label="目标"
          width="80">
        </el-table-column>
        <el-table-column
          prop="zip"
          label="已完成"
          width="80" class="red">
        </el-table-column>
      </el-table-column>
       <el-table-column label="二月">
        <el-table-column
          prop="address"
          label="目标"
          width="80">
        </el-table-column>
        <el-table-column
          prop="zip"
          label="已完成"
          width="80" class="red">
        </el-table-column>
      </el-table-column>
       <el-table-column label="三月">
        <el-table-column
          prop="address"
          label="目标"
          width="80">
        </el-table-column>
        <el-table-column
          prop="zip"
          label="已完成"
          width="80" class="red">
        </el-table-column>
      </el-table-column>
       <el-table-column label="四月">
        <el-table-column
          prop="address"
          label="目标"
          width="80">
        </el-table-column>
        <el-table-column
          prop="zip"
          label="已完成"
          width="80" class="red">
        </el-table-column>
      </el-table-column>
       <el-table-column label="五月">
        <el-table-column
          prop="address"
          label="目标"
          width="80">
        </el-table-column>
        <el-table-column
          prop="zip"
          label="已完成"
          width="80" class="red">
        </el-table-column>
      </el-table-column>
  </el-table>
     </div>
         </el-col>
       </el-row>
    </div>
</template>
<script>

import Left from '../components/Left';
export default {
    name:'xiansou',
     data() {
      return {
        tableData: [{
          date: '2016',
          name: '新增商机数',
          province: '本人',
          city: '普陀区',
          address: '50/条',
          zip: '65/条'
        }, {
          date: '2016',
          name: '新增跟单数',
          province: '本人',
          city: '普陀区',
          address: '50/条',
          zip: '65/条'
        }, {
          date: '2016',
          name: '跟单预收款',
          province: '本人',
          city: '普陀区',
          address: '50/条',
          zip: '65/条'
        }, {
          date: '2016',
          name: '赢单数量',
          province: '本人',
          city: '普陀区',
          address: '10000',
          zip: '2003'
        }, {
          date: '2016',
          name: '合同回款金额',
          province: '本人',
          city: '普陀区',
         address: '50/条',
          zip: '65/条'
        }, {
          date: '2016',
          name: '合同金额',
          province: '本人',
          city: '普陀区',
          address: '10000',
          zip: '2003'
        }, {
          date: '2016',
          name: '产品A销量',
          province: '本人',
          city: '普陀区',
          address: '50/单',
          zip: '65/单'
        }, {
          date: '',
          name: '--',
          province: '',
          city: '',
          address: '',
          zip: ''
        }, {
          date: '',
          name: '--',
          province: '',
          city: '',
          address: '',
          zip: ''
        }, {
          date: '',
          name: '--',
          province: '',
          city: '',
          address: '',
          zip: ''
        }, {
          date: '',
          name: '--',
          province: '',
          city: '',
          address: '',
          zip: ''
        }]
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
      /* background-color: #f6f6f7; */
    }
    .blu{
       border-bottom: cyan 1.5px solid;
   }
    ::v-deep .el-menu--horizontal>.el-submenu .el-submenu__title{
        margin-top: 10px;
    height: 22px;
     line-height: normal;
    
   }
   ::v-deep .el-table td, ::v-deep .el-table th{
        padding: 0px 0;
   }
   ::v-deep .el-table th>.cell{
     text-align: center;
   }
   ::v-deep .el-table_1_column_5_column_7, ::v-deep .el-table_1_column_8_column_10, ::v-deep .el-table_1_column_11_column_13, ::v-deep .el-table_1_column_14_column_16, ::v-deep .el-table_1_column_17_column_19{
      color: #CC0000;
   }
    /* ::v-deep .el-table_2_column_15_column_17{
      color: #CC0000;
   }
    ::v-deep .el-table_2_column_12_column_20{
      color: #CC0000;
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
     .yuan{
     margin: 5px 5px;
     padding: 2px 5px;
     /* width: 150px; */
     /* background-color: aliceblue; */
     border: 0.5px darkgray solid;
     display: inline-block;
     border-radius: 5px;
     font-size: 10px;
     text-align: center;
   }
   .yuan strong{
       font-size: 15px;
   }
   .yuan p{
       display: inline-block;
       
   }
   ::v-deep .el-table .cell{
         line-height: 30px;
   }
   .red{
       margin-left: 5px;
       color: #CC0000;
   }
   .rig{
       float: right;
       margin-right: 20px;
       padding: 5px 10px;
       border: 0.5px darkgray solid;
       margin-top: 12px;
       font-size: 10px;
   }
</style>