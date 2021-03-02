<template>
    <div class="app">
       <el-row class="tac">
           <el-col :span="1"><div class="grid-content bg-purple">
            <Left></Left>
           </div>
         </el-col>
            <el-col :span="4"><div class="grid-content bg-purple">
                <div class="blu">&nbsp;&nbsp;
                    <i class="el-icon-printer" style="margin-top:8px;margin-left:5px;"></i>&nbsp;&nbsp;
                      <!-- <el-select v-model="value" placeholder="客户主线">
                    <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
                    </el-option>
                </el-select> -->
                <select class="select">
                    <option  value="0"  selected= "selected">客户主线</option>
                    <option  value="1">主分类</option>
                    <option  value="2">行业</option>
		        </select>
                </div>
                <div class="da-div">
                    <br>
                    <el-collapse accordion>
                    <el-collapse-item>
                        <template slot="title">
                        <i class="header-icon el-icon-folder"></i>&nbsp;&nbsp;区域代理
                        </template>
                        <div class="ddd">&nbsp;&nbsp;<i class="el-icon-location-outline"></i>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;四川省</div>
                        <div>&nbsp;&nbsp;<i class="el-icon-location-outline"></i>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;福建省</div>
                        <div>&nbsp;&nbsp;<i class="el-icon-location-outline"></i>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;福建省</div>
                        <div>&nbsp;&nbsp;<i class="el-icon-location-outline"></i>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;黑龙江省</div>
                        <div>&nbsp;&nbsp;<i class="el-icon-location-outline"></i>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;辽宁省</div>
                        <div>&nbsp;&nbsp;<i class="el-icon-location-outline"></i>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;吉林省</div>
                        <div>&nbsp;&nbsp;<i class="el-icon-location-outline"></i>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;浙江省</div>                        
                  </el-collapse-item>
                    </el-collapse>
                    <el-collapse accordion>
                    <el-collapse-item>
                    <template slot="title">
                        <i class="header-icon el-icon-folder"></i>&nbsp;&nbsp;普通客户
                        </template>
                    </el-collapse-item>
                    </el-collapse>    
                </div>
                </div></el-col>
            <el-col :span="18"><div class="grid-content bg-purple">
                <!-- <div class="blu">
                    <i class="el-icon-printer" style="margin-top:8px;margin-left:5px;margin-bottom:9px;"></i>&nbsp;&nbsp;
                
                </div> -->
                 <div class="blu">
         <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
                      <!-- <i class="el-icon-printer" style="margin-top:8px;margin-left:5px;"></i>&nbsp;&nbsp; -->
                    <el-submenu index="2">
    <template slot="title">我的日程</template>
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
      <span class="yuan">全部客户<br><strong>268</strong></span>
      <span class="yuan">今日新增<br><strong>25</strong></span>
      <span class="yuan">今日归还<br><strong>16</strong></span>
      <span class="yuan">今天生日<br><strong>5</strong></span>
      <input type="text" placeholder="客户名称,地区,联系人">
   </el-menu>
          </div>
                <p class="ppppp">&nbsp;&nbsp;已选6条&nbsp;&nbsp;
                   <el-button class="bt1" :plain="true" @click="open2">领用</el-button>
                   <el-button class="bt1" @click="drawer = true" type="primary" style="margin-left: 16px;">
                    分配
                  </el-button>
                  <el-drawer
                      :visible.sync="drawer"
                      :direction="direction"
                      :before-close="handleClose1">
                      <img src="../assets/img/kals.png" width="100%">
                  </el-drawer>
                   <el-button class="bt1" @click="drawer = true" type="primary" style="margin-left: 16px;">
                    发短信
                  </el-button>
                  <el-drawer
                      :visible.sync="drawer"
                      :direction="direction"
                      :before-close="handleClose1">
                      <img src="../assets/img/kals.png" width="100%">
                  </el-drawer>
                  <span class="youbian">
                    <el-button type="text" @click="dialog = true"><i class="el-icon-circle-plus-outline"></i></el-button>
                    <el-drawer
                      title="新建公告池客户"
                      :before-close="handleClose"
                      :visible.sync="dialog"
                      direction="ltr"
                      custom-class="demo-drawer"
                      ref="drawer"
                      >
                      <div class="demo-drawer__content">
                        <el-form :model="form">
                          <p class="ppppp">&nbsp;&nbsp;联系人信息</p>
                          <el-form-item label="客户名称" :label-width="formLabelWidth">
                            <el-input v-model="form.name1" autocomplete="off"></el-input>
                          </el-form-item><br>
                          <el-form-item label="行业" :label-width="formLabelWidth">
                            <el-select v-model="form.region" placeholder="所属行业">
                              <el-option label="营销" value="营销"></el-option>
                              <el-option label="市场" value="市场"></el-option>
                              <el-option label="工程开发" value="工程开发"></el-option>
                            </el-select>
                          </el-form-item><br>
                            <el-form-item label="地区" :label-width="formLabelWidth">
                            <el-select v-model="form.region1" placeholder="城市">
                              <el-option label="上海" value="上海"></el-option>
                              <el-option label="北京" value="北京"></el-option>
                              <el-option label="长沙" value="长沙"></el-option>
                            </el-select>
                          </el-form-item><br>
                          <el-form-item label="地区" :label-width="formLabelWidth">
                            <el-input v-model="form.name" autocomplete="off"></el-input>
                          </el-form-item>
                        </el-form>
                        <div class="demo-drawer__footer">
                          <br><br><br><br><br>
                          <el-button @click="cancelForm">取 消</el-button>
                          <el-button type="primary" @click="$refs.drawer.closeDrawer()" :loading="loading">{{ loading ? '提交中 ...' : '确 定' }}</el-button>
                        </div>
                      </div>
                      
                  </el-drawer>
                 
                   <el-button @click="drawer = true" type="primary" style="margin-left: 16px;">
                    <i class="el-icon-document-checked"></i>
                  </el-button>
                  <el-drawer
                      :visible.sync="drawer"
                      :direction="direction"
                      :before-close="handleClose1">
                      <img src="../assets/img/kkk.png" width="100%">
                  </el-drawer>
                  
                 <el-button @click="drawer = true" type="primary" style="margin-left: 16px;">
                    <i class="el-icon-guide"></i>
                  </el-button>

                  <el-drawer
                    title="我是标题"
                    :visible.sync="drawer"
                    :with-header="false">
                     <img src="../assets/img/kkk2.png" width="100%">
                  </el-drawer>
                  </span>
                </p>
                <el-table
                ref="multipleTable"
                :data="tableData"
                tooltip-effect="dark"
                style="width: 100%"
                height="350"
                border=""
                @selection-change="handleSelectionChange">
                <el-table-column
                fixed
                type="selection"
                width="55">
                </el-table-column>
                <el-table-column
                prop="aname"
                label="客户名称"
                width="150">
                </el-table-column>
                <el-table-column
                prop="name"
                label="行业"
                width="120">
                </el-table-column>
                <el-table-column
                prop="phone"
                label="来源"
                width="120">
                </el-table-column>
                <el-table-column
                prop="money"
                label="客户类型"
                width="120">
                </el-table-column>
                <el-table-column
                prop="time"
                label="销售阶段"
                width="120">
                </el-table-column>
                <el-table-column
                prop="lian"
                label="联系人"
                width="70">
                </el-table-column>
                 <el-table-column
                prop="iphone"
                label="电话"
                width="120">
                </el-table-column>
                 <el-table-column
                prop="yuan"
                label="入池原因"
                width="210">
                </el-table-column>
                 <el-table-column
                prop="date"
                label="创建时间"
                width="120">
                </el-table-column>
                 <el-table-column
                prop="zip"
                label="领用/分配日子"
                wirizidth="180">
                </el-table-column>
                 <el-table-column
                prop="jindu"
                label="历史跟进记录"
                width="120">
                </el-table-column>
                 <el-table-column
                prop="guan"
                label="关联项"
                width="120">
                </el-table-column>
                 <el-table-column
                prop="moy"
                label="客户价值"
                width="120">
                </el-table-column>
                 <el-table-column
                prop="bei"
                label="备注"
                width="180">
                </el-table-column>
                 <el-table-column
                prop="ren"
                label="创建人"
                width="120">
                </el-table-column>  
                 <el-table-column
                prop="yi"
                label="社会统一信用编码"
                width="150">
                </el-table-column>
                 <el-table-column
                prop="dizhi"
                label="地址"
                width="210">
                </el-table-column>
            </el-table>

                </div></el-col>
        </el-row>
    </div>
</template>
<script>
import Left from '../components/Left';
export default {
    name:'kehu',
      data() {
      return {
        table: false,
      dialog: false,
      loading: false,
        tableData: [{
          aname:'广西梧州万枫酒店',
          date: '2019-02-18',
          name: '餐饮业',
          province: '1',
          city: '1',
          address: '1',
          zip: '共两条',
          lian:'王总',
          iphone:'13734567777',
          yuan:'填充文字填充文字填充文字',
          jindu:'共3条',
          guan:'共3条',
          moy:'',
          bei:'---',
          ren:'销售1部-厂长',
          yi:'---',
          dizhi:'武汉市华府大道南端135号'

        }, {
         aname:'广西梧州万枫酒店',
          date: '2019-02-18',
          name: '餐饮业',
          province: '网络咨询',
          city: '独资公司',
          address: '意向客户',
          zip: '共两条',
          lian:'王总',
          iphone:'13734567777',
          yuan:'填充文字填充文字填充文字',
          jindu:'共3条',
          guan:'共3条',
          moy:'',
          bei:'---',
          ren:'销售1部-厂长',
          yi:'---',
          dizhi:'武汉市华府大道南端135号'
        }, {
         aname:'广西梧州万枫酒店',
          date: '2019-02-18',
          name: '餐饮业',
          province: '网络咨询',
          city: '独资公司',
          address: '意向客户',
          zip: '共两条',
          lian:'王总',
          iphone:'13734567777',
          yuan:'填充文字填充文字填充文字',
          jindu:'共3条',
          guan:'共3条',
          moy:'',
          bei:'---',
          ren:'销售1部-厂长',
          yi:'---',
          dizhi:'武汉市华府大道南端135号'
        }, {
         aname:'广西梧州万枫酒店',
          date: '2019-02-18',
          name: '餐饮业',
          province: '网络咨询',
          city: '独资公司',
          address: '意向客户',
          zip: '共两条',
          lian:'王总',
          iphone:'13734567777',
          yuan:'填充文字填充文字填充文字',
          jindu:'共3条',
          guan:'共3条',
          moy:'',
          bei:'---',
          ren:'销售1部-厂长',
          yi:'---',
          dizhi:'武汉市华府大道南端135号'
        }, {
          aname:'广西梧州万枫酒店',
          date: '2019-02-18',
          name: '餐饮业',
          province: '网络咨询',
          city: '独资公司',
          address: '意向客户',
          zip: '共两条',
          lian:'王总',
          iphone:'13734567777',
          yuan:'填充文字填充文字填充文字',
          jindu:'共3条',
          guan:'共3条',
          moy:'',
          bei:'---',
          ren:'销售1部-厂长',
          yi:'---',
          dizhi:'武汉市华府大道南端135号'
        }, {
        aname:'广西梧州万枫酒店',
          date: '2019-02-18',
          name: '餐饮业',
          province: '网络咨询',
          city: '独资公司',
          address: '意向客户',
          zip: '共两条',
          lian:'王总',
          iphone:'13734567777',
          yuan:'填充文字填充文字填充文字',
          jindu:'共3条',
          guan:'共3条',
          moy:'',
          bei:'---',
          ren:'销售1部-厂长',
          yi:'---',
          dizhi:'武汉市华府大道南端135号'
        }, {
          aname:'广西梧州万枫酒店',
          date: '2019-02-18',
          name: '餐饮业',
          province: '网络咨询',
          city: '独资公司',
          address: '意向客户',
          zip: '共两条',
          lian:'王总',
          iphone:'13734567777',
          yuan:'填充文字填充文字填充文字',
          jindu:'共3条',
          guan:'共3条',
          moy:'',
          bei:'---',
          ren:'销售1部-厂长',
          yi:'---',
          dizhi:'武汉市华府大道南端135号'
        }],
         multipleSelection: [],
            drawer: false,
        direction: 'rtl',
          form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      },
      formLabelWidth: '80px',
      timer: null,
      };
      
    },
      methods: {
      toggleSelection(rows) {
        if (rows) {
          rows.forEach(row => {
            this.$refs.multipleTable.toggleRowSelection(row);
          });
        } else {
          this.$refs.multipleTable.clearSelection();
        }
      },
      handleSelectionChange(val) {
        this.multipleSelection = val;
      },
       open2() {
        this.$message({
          message: '已领用成功，立即使用',
          type: 'success'
        });
      },
       handleClose1(done) {
        this.$confirm('确认关闭？')
          .then(_ => {
            done();
          })
          .catch(_ => {});
      },
       handleClose(done) {
      if (this.loading) {
        return;
      }
      this.$confirm('确定要提交表单吗？')
        .then(_ => {
          this.loading = true;
          this.timer = setTimeout(() => {
            done();
            // 动画关闭需要一定的时间
            setTimeout(() => {
              this.loading = false;
            }, 400);
          }, 2000);
        })
        .catch(_ => {});
    },
    cancelForm() {
      this.loading = false;
      this.dialog = false;
      clearTimeout(this.timer);
    }
  } ,components:{
      Left,
    },created() {
        this.axios.get("http://yapi.dapengjiaoyu.com/mock/380/order").then((res)=>{
            for(let sb=0;sb<10;sb++){
                 this.tableData.push(res.data.data[sb]);
            }
            console.log(res);
        });
    }
      }

</script>
<style scoped>
  ::-webkit-scrollbar {
     width: 0 !important;
   }
   ::-webkit-scrollbar {
     width: 0 !important;height: 0;
   }
   ::v-deep .el-button el-button--primary{
     padding: 5 10px;
     color: black;
   }
   
   *{
       margin: 0 auto;
       padding: 0 0;
       /* background-color: rgba(250, 251, 252, 1); */
   }
   .ddd{
       margin-top: 10px;    
   }
   .el-icon-arrow-right:before{
    content: "";
    }
    ::v-deep .el-icon-location-outline:before{
          background-color: #409EFF;
          border-color: #409EFF;
          color: black;
          padding: 1px 2px;
          border-radius: 3px;
    }
    .youbian{
      float: right;
    }
   .select{
       padding: 3px 5px;
       margin: 8px 0;
       border-radius:4px; 
       width: 70%;
       font-size: 10px;
   }
  .sele{
        padding: 3px 5px;
       margin: 8px 0;
       border-radius:4px; 
       width: 10%;
       font-size: 10px;
       /* border-right: #99a9bf 0.5px solid; */
  }
   .blu{
       border-bottom: cyan 1.5px solid;
   }
  .el-row {
    margin-bottom: 20px;
  }
  .el-icon-printer{
      font-size: 20px;
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .el-collapse-item__header {
    display: -webkit-box;
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    height: 28px;
    line-height: 48px;
    background-color: #FFF;
    color: #303133;
    cursor: pointer;
    border-bottom: 1px solid #EBEEF5;
    font-size: 10px;
    font-weight: 500;
    transition: border-bottom-color .3s;
    outline: 0;
}
.da-div{
    height: 500px;
    margin: 0 0 20px 10px;
    background-color: white;
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
   .rig{
       float: right;
       margin-right: 20px;
       padding: 5px 10px;
       border: 0.5px darkgray solid;
       margin-top: 12px;
       font-size: 10px;
   }
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
::v-deep .el-menu--horizontal>.el-submenu .el-submenu__title{
    height: 22px;
     line-height: normal;
    margin-top: 10px;
   }
 input{
      width: 20%;
      border: 0.5px rgba(0, 168, 255, 1) solid;
      float: right;
      margin-top: 10px;
  }
  .ppppp{
    color: black;
    padding: 10px 0;
    font-size: 12px;
  }
  .bt1{
    padding: 3px 10px;
    color: black;
  }
</style>