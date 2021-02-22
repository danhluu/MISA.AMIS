<style scoped>
.isHide {
  display: none;
}
.m-dialog {
    position: relative;
    z-index: 999;
    /* display: none; */
}

.dialog-modal{
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: black;
  opacity: 0.7;
}

.dialog-content {
  position: fixed;
  border-radius: 5px;
  width: 1015px;
  background-color: #fff;
  left: calc(50% - 464px);
  top: calc(50% - 320px);
}

.dialog-header {
  position: relative;
  height: 40px;
  line-height: 60px;
  padding-left: 32px;
  display: flex;
}

.dialog-header-title{
    font-size: 24px;
    font-weight: bold;
    width: 280px;
}

.flex-checkbox{
    display: flex;
    margin-left: 20px;
    width: 160px;
}
    .flex-checkbox input{
        width: 20px;
        height: 20px;
        margin-top: 20px;
    }
    .flex-checkbox span{
        margin-left: 8px;
    }
.supplier-checkbox{

}

.dialog-header-close {
    display: flex;
    position: absolute;
    top: 10px;
    right: 16px;
    width: 50px;
}
    .dialog-header-close .question{
        background: url('../../assets/img/Sprites.64af8f61.svg') no-repeat -89px -145px;
        width: 22px;
        height: 22px;
    }
    .dialog-header-close .closePopup2{
        background: url('../../assets/img/Sprites.64af8f61.svg') no-repeat -147px -147px;
        width: 18px;
        height: 18px;
        margin-left: 8px;
        text-align: center;
        position: absolute;
        right: 0;
        top: 2px;
        
    }

.dialog-body {
  margin-top: 24px;
  padding: 0 16px 16px 32px;
  position: relative;
}
    .column-md-1{
        display: flex;
        margin-top: 8px;
    }
        .column-md-1 .left-element{
            display: flex;
            width: 452px;
        }
            .column-md-1 .left-element .left-left{
                width: 165px;
            }
                .column-md-1 .left-element .left-left input{
                    width: 100%;
                }
            .column-md-1 .left-element .left-right{
                margin-left: 16px;
                width: 270px;
            }
                .column-md-1 .left-element .left-right input{
                    width: 100%;
                }  
    .text-title{
        font-family: 'notosans-regular';
        font-weight: bold;
    } 
    .right-element{
        margin-left: 32px;
        display: flex;
    }
        .right-element .right-right{
            margin-left: 20px;
        }
            .right-element .right-right .radio-box{
                display: flex;
                /* position: relative; */
            }
                .female{
                    margin-left: 20px;
                    display: flex;
                }
                .male{
                    display: flex;
                }
                .gender-text{
                    margin: 8px 0 0 8px;
                }
        .margin-4px{
            margin-top: 4px;
        }
        .left-content select{
            width: 460px;
        }
        
        .cmnd{
            width: 280px;
        }
        .right-date{
            margin-left: 8px;
        }
        .left-input-cd{
            width: 452px;
        }
        .right-cmnd{
            width: 462px;
        }
        .right-cmnd input{
            width: 100%;
        }
    /**Tab */
    /* định dạng thẻ div chưa các button tab */
    div.tab {
        overflow: hidden; 
        width: 300px;
        height: 40px;
        display: flex;
        margin-top: 24px;
    }
        .contact{
            width: 100px;
            height: 32px;
            border: 1px solid #d8d6d6;
            margin-top: 8px;
        }
        
        .bank-account{
            width: 280px;
            height: 32px;
            margin-left: 4px;
            margin-top: 8px;
            border: 1px solid #d8d6d6;
        }
        .active{
            height: 40px;
            margin-top: 0;
            background-color: #cbe4fc;
        }
    
    /* định dạng các button tab */
    div.tab button {
        cursor: pointer;
        transition: 0.3s;
        font-size: 17px;
    }
    
    /* đổi màu khi một button tab được hover */
    div.tab button:hover {
        background-color: #ddd;
    }
    
    
    /* định dạng nội dung hiển thị */
    .tabcontent {
        width: 928px;
        height: 200px;
        display: none;
        padding: 4px 12px;
        border: 1px solid #ccc;
    }
    
.dialog-footer {
  display: flex;
  width: 100%;
  height: 60px;
  border-radius: 0 0 5px 5px;
  align-items: center;
  /* justify-content: flex-end; */
  padding: 12px 24px;
  box-sizing: border-box;
  
}
    .add{
        position: absolute;
        bottom: 0px;
        right: 30px;
        
    }
    .m-btn{
        border: 1px solid #464545;
        border-radius: 4px;
        height: 40px;
        width: 130px;
        margin-left: 8px;
        margin-bottom: 20px;
        font-weight: bold;
    }
    .m-btn-default{
        width: 70px;
    }
    .m-btn-add{
        margin-left: 12px;
        background-color: #2d9f1d;
        color: #ffffff;
        border: none;
    }
input{
    /* margin-top: 4px; */
}
input[type="radio"]{
    width: 24px;
    margin-left: 0;
    color: #2d9f1d;
}
            
input[type="date"]{
    width: 150px;
    height: 32px;
    padding-left: 20px;
}
select{
    height: 36px;
    padding-left: 8px;
}
.validate{
    color: red;
}
.margin-8px{
    margin-top: 8px;
    margin-left: 8px;
}
.width-100{
    width: 99%;
}
.display-flex{
    display: flex;
}
.margin-left-4px{
    margin-left: 8px;
}
.table-bank-table{
    background-color: #eaebef;
}
    tr,td{
        border-bottom: 1px solid #464545;
    }
.margin-top-8px{
    margin-top: 8px;
}
.btn-option{
    width: 120px;
    border: 2px solid #464545;
    margin-top: 12px;
    border-radius: 5px;
}
.td-icon{
    background: url('../../assets/img/Sprites.64af8f61.svg') no-repeat -464px -313px;
	width: 15px;
	height: 15px;
}
hr{
    margin: 40px 0 0 0;
    width: 954px;
}
</style>
<template>
  <div>
    <div class="m-dialog dialog-detail" title="Thông tin nhân viên" :class="{ isHide: isHide }">
      <div class="dialog-modal"></div>
      <div class="dialog-content">
        <div class="dialog-header">
          <div class="dialog-header-title">THÔNG TIN NHÂN VIÊN</div>
          <div class="customer-checkbox flex-checkbox">
              <input type="checkbox">
              <span>Là khách hàng</span>
          </div>
          <div class="supplier-checkbox flex-checkbox">
              <input type="checkbox">
              <span>Là nhà cung cấp</span>
          </div>
          <div class="dialog-header-close">
            <button class="question"></button>
            <button class="closePopup2" @click="btnCancelOnClick"></button>
          </div>
        </div>
        <div class="dialog-body">
            <div class="column-md-1">
                <div class="left-element">
                    <div class="left-left">
                        <div class="text-title">Mã <span class="validate"> * </span></div>
                        <div class="left-input margin-4px">
                            <input v-if="employee.employeeCode!=null" type="text" placeholder="" v-model="employee.employeeCode">
                            <input v-else type="text" placeholder="" v-model="eCode">
                        </div>
                    </div>
                    <div class="left-right">
                        <div class="text-title">Tên <span class="validate"> * </span></div>
                        <div class="right-input margin-4px">
                            <input type="text" placeholder="" v-model="employee.fullName">
                        </div>
                    </div>
                </div>
                <div class="right-element">
                    <div class="right-left">
                        <div class="text-title">
                            Ngày Sinh
                        </div>
                        <input type="date" class="margin-4px" v-model="employee.dateOfBirth">
                    </div>
                    <div class="right-right">
                        <div class="text-title">Giới tính</div>
                        <div class="radio-box margin-4px">
                            <div class="male">
                                <input type="radio" name="gender" value="1" v-model="employee.Gender">
                                <span class="gender-text">Nam</span>
                            </div>
                            <div class="female">
                                <input type="radio" name="gender" value="0" v-model="employee.Gender">
                                <span class="gender-text">Nữ</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="column-md-1">
                <div class="left-element">
                    <div class="left-content left-left ">
                        <div class="text-title">Đơn vị <span class="validate">*</span></div>
                        <div class="left-input margin-4px" >
                            <select v-model="employee.departmentId">
                                <option v-for="dp in departments" :key="dp.departmentId" :value="dp.departmentId">
                                    {{dp.departmentName}}
                                </option>
                            </select>
                        </div>
                    </div>
                    
                </div>
                <div class="right-element">
                    <div class="right-left">
                        <div class="text-title">
                            Số CMND
                        </div>
                        <input type="text" class="margin-4px cmnd" v-model="employee.identifyNumber">
                    </div>
                    <div class="right-date">
                        <div class="text-title">Ngày cấp</div>
                        <div class="radio-box">
                            <input type="date" class="margin-4px" v-model="employee.identifyDate">
                        </div>
                    </div>
                </div>
            </div>
            <div class="column-md-1">
                <div class="left-element">
                    <div class="left-content left-left ">
                        <div class="text-title">Chức danh</div>
                        <div class="left-input-cd margin-4px">
                            <input type="text" class="" v-model="employee.positionName">
                        </div>
                    </div>
                    
                </div>
                <div class="right-element">
                    <div class="right-cmnd">
                        <div class="text-title ">
                            Nơi cấp
                        </div>
                        <input type="text" class="margin-4px cmnd" v-model="employee.identifyPlace">
                    </div>
                </div>
            </div>
            <div class="column-md-2">
                <div class="tab">
                    <button @click="showContent('Contact')" class="tablinks active contact">Liên hệ</button>
                    <button @click="showContent('BankInfor')" class="tablinks bank-account">Tài khoản ngân hàng</button>
                </div>
                    
                <div id="Contact" class="tabcontent">
                    <div class="margin-8px">
                        <div class="text-title">Địa chỉ</div>
                        <input class="margin-4px width-100" type="text" name="" id="" v-model="employee.address">
                    </div>
                    <div class="margin-8px display-flex">
                        <div class="col-1">
                            <div class="text-title">ĐT di dộng</div>
                            <input class="margin-4px" type="text" v-model="employee.mobilePhone">
                        </div>
                        <div class="col-1 margin-left-4px">
                            <div class="text-title">ĐT cố định</div>
                            <input class="margin-4px" type="text" v-model="employee.landlinePhone">
                        </div>
                        <div class="col-1 margin-left-4px">
                            <div class="text-title">Email</div>
                            <input class="margin-4px" type="text" v-model="employee.email">
                        </div>
                    </div>
                    
                </div>
                
                <div id="BankInfor" class="tabcontent">
                   <div class="table-bank">
                       <table class="table-bank-table margin-top-8px">
                           <tr>
                               <th>SỐ TÀI KHOẢN</th>
                               <th>TÊN NGÂN HÀNG</th>
                               <th>CHI NHÁNH</th>
                               <th>TỈNH/TP CỦA NGÂN HÀNG</th>
                               <th></th>
                           </tr>

                           <tr>
                               <td><input type="text" v-model="employee.bankNumber"></td>
                               <td><input type="text" v-model="employee.bankName"></td>
                               <td><input type="text" v-model="employee.bankBranch"></td>
                               <td><input type="text" v-model="employee.bankPlace"></td>
                               <td><div class="td-icon"></div></td>
                           </tr>
                       </table>
                   </div>
                   <div class=" display-flex">
                       <button class="btn-option">Thêm dòng</button>
                       <button class="btn-option margin-8px">Xoá hết dòng</button>
                   </div>
                </div>
               
            </div>

            <hr>
        </div>
        <div class="dialog-footer">
          <button id="btnCancel" class="m-btn m-btn-default m-btn-cancel" v-on:click="btnCancelOnClick">
            Hủy
          </button>
          <div class="add display-flex">
              <button id="btnUpdate" @click="UpdateEmployee"  class="m-btn m-btn-default">Cất</button>
              <button id="btnAdd" @click="saveEmployee" class="m-btn m-btn-add">Cất và thêm</button>
          </div>
          
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import * as axios from "axios";
export default {
    props: ['isHide','employee'],
    methods:{
        btnCancelOnClick() {
            this.$emit('closePopup',true);
            this.eCode="";
            // this.isHide = true;
        },
        showContent(id){
            var buttons = document.getElementsByClassName('tablinks');
            var contents = document.getElementsByClassName('tabcontent');
            for (var i = 0; i < contents.length; i++) {
                contents[i].style.display = 'none';
            }
            var content = document.getElementById(id);
            content.style.display = 'block';
            for (var j = 0; j < buttons.length; j++) {
                buttons[j].addEventListener("click", function(){
                    // var id = this.textContent;
                    for (var j = 0; j < buttons.length; j++) {
                        buttons[j].classList.remove("active");
                    }
                    this.className += " active";
                });
            }
        },
        async saveEmployee() {
            var response = null;
            if(this.eCode!=""){
                this.employee.employeeCode=this.eCode;
            }
            response = await axios.post("https://localhost:44356/api/Employees", this.employee);
            
            console.log(response);
            this.eCode="";
            this.$emit('closePopup',true)
            location.reload();
        },
        async UpdateEmployee() {
            // this.employee.status=1;
            const update = await axios.put("https://localhost:44356/api/Employees", this.employee);
            
            console.log(update);
            this.$emit('closePopup',true)
            console.log(this.employee)
        }
    },
    data(){
        return{
            departments: [
            ],
            employees:[],
            eCode:"",
            emCode: []
        };
    },
    async created(){
        const dp = await axios.get("https://localhost:44356/api/Departments");
        const e = await axios.get("https://localhost:44356/api/Employees");
        
        this.departments = dp.data;
        this.employees = e.data;
        for(let i = 0;i<this.employees.length-1;i++){
            if(this.employees[i].employeeCode!=null)
            this.emCode[i]=this.employees[i].employeeCode;

            var x = this.emCode[i].split("KH");
            this.emCode[i]=Number(x[1]);
        }
        this.emCode.sort(function(a, b){return a - b});
        console.log(this.emCode);
        this.eCode="KH"+(this.emCode[this.emCode.length-1]+1);
        console.log(this.eCode);
        console.log(this.departments[0]);
    },
    
    

};

</script>
