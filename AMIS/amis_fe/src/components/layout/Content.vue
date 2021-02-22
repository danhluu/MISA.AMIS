<template>
    <div class="content">
        <div class="content-title">
            <div class="title">Nhân Viên</div>
            <button @click="btnAddOnClick()" class="btn-add">Thêm</button>
            <EmployeeDetail :employee="selectedEmployee" @closePopup="closePopup" :isHide="isHideParent" />
        </div>
        
        <button class="back-to-nav">
            <div class="btn-nav"></div>
            <div class="text-nav">Tất cả danh mục</div>
        </button>
        <div class="content-table">
            <div class="content-search general-input">
                <input type="text" placeholder="Tìm theo mã, tên nhân viên">
                <div class="search-icon"></div>
            </div>
            <div class="table-data" style="overflow-x:auto;">
                <table id="tblEmployee" >
                    <thead>
                        <tr class="title" style="width: 100%">
                            <th style="width: 9%">Mã Nhân Viên</th>
                            <th style="width: 20%">Tên Nhân Viên</th>
                            <th>Chức Danh</th>
                            <th style="width: 20%">Tên Đơn Vị</th>
                            <th>Số Tài Khoản</th>
                            <th style="width: 13%">Tên Ngân Hàng</th>
                            <th style="width: 9%">Trạng Thái</th>
                            <th>Chi Nhánh</th>
                            <th>Chức Năng</th>
                        </tr>
                    </thead>
                    <tbody >
                        <tr  v-for="employee in employees"
                            :key="employee.employeeId">
                            <td>{{ employee.employeeCode }}</td>
                            <td>{{ employee.fullName }}</td>
                            <td>{{employee.positionName}}</td>
                            <td>{{employee.departmentName}}</td>
                            <td>{{employee.bankNumber}}</td>
                            <td>{{employee.bankName}}</td>
                            <td v-if="employee.status==1">Đang Sử Dụng</td>
                            <td v-else>Ngưng Sử Dụng</td>
                            <td>{{employee.bankBranch}}</td>
                            <td class="function" >
                                <button @click="rowOnClick(employee)" class="edit-column">Sửa</button>
                                <button class="btn-more" v-on:click="showMore(employee.employeeId)"> 
                                    <div class="more-icon"></div>
                                </button>
                                <div class="list-function display-none" :id="employee.employeeId">
                                    <button class="dupplicate element ">Nhân Bản</button>
                                    <button class="Delete element" @click="btnDeleteOnClick(employee)">Xoá</button>
                                    <button class="set-status element">Ngừng sử dụng</button>
                                    <EmployeeDelete  :employee="selectedEmployee" :isHideDelete="isHideDelete" @closeDelete="closeDelete" />
                                </div>
                            </td>
                        </tr>
                        
                    </tbody>
                </table>
                
            </div>
            <div class="pagination">
                <div class="total">Tổng số: <span>94</span> bản ghi</div>
                <div class="paging-right">
                    <div class="filter">
                        <select name="" id="">
                            <option value="">20 bản ghi trên 1 trang</option>
                            <option value="">50 bản ghi trên 1 trang</option>
                            <option value="">100 bản ghi trên 1 trang</option>
                        </select>
                    </div>
                    <button class="previous">Trước</button>
                    <div class="paging">
                        <button style="border: 1px solid #000; font-weight: bold;" class="paging-number">1</button>
                        <button class="paging-number">2</button>
                        <button class="paging-number">3</button>
                        <button class="paging-number">...</button>
                        <button class="paging-number">5</button>
                    </div>
                    <button class="next">Sau</button>
                </div>
            </div>
        </div>
        
    </div>
</template>

<script>
import * as axios from "axios";
import EmployeeDetail from "@/views/dictionary/EmployeeDetail";
import EmployeeDelete from "@/views/dictionary/EmployeeDelete";
export default {
    name: 'App',
    components: {
        EmployeeDetail,
        EmployeeDelete
    },
    methods:{
        showMore(employeeId){
            var x = document.getElementById(employeeId);
            console.log(x);
            x.classList.toggle('display-none');
        },
        btnAddOnClick(){
            this.selectedEmployee ={};
            this.isHideParent = false;
        },
        
        closePopup(value) {
            this.isHideParent = value;
        },
        closeDelete(value){
            this.isHideDelete = value;
        },
        btnDeleteOnClick(employee){
            this.isHideDelete = false;
            this.selectedEmployee = employee;
            console.log("Delete");
            console.log(employee)
        },
        rowOnClick(employee){
            this.isHideParent = false;
            this.selectedEmployee = employee;
            this.selectedEmployee.dateOfBirth = new Date(this.selectedEmployee.dateOfBirth).toISOString().substr(0, 10);
            this.selectedEmployee.identifyDate = new Date(this.selectedEmployee.identifyDate).toISOString().substr(0, 10);
            // this.selectedEmployee.JoinDate = new Date(this.selectedEmployee.JoinDate).toISOString().substr(0, 10);
            // console.log(this.test);
            console.log(this.selectedEmployee.dateOfBirth);
            // this.selectedEmployee.FullName = employee.FullName;
            // this.selectedEmployee.EmployeeCode = employee.EmployeeCode;
            //this.$emit('setTextEmployee',employee)
            console.log(employee)
        },
    },
    data(){
        return{
            isHideParent: true,
            isHideDelete: true,
            employees: [
            ],
            departments:[
            ],
            selectedEmployee:{
                
            }
        }
    },
    async created(){
        const response = await axios.get("https://localhost:44356/api/Employees");
        const resDp = await axios.get("https://localhost:44356/api/Departments")
        console.log(response.data[0]);
        // console.log(resDp.data[0]);
        this.employees = response.data;
        this.departments = resDp.data;
        for(let i =0;i<this.employees.length;i++){
            // if(this.employees[i].status==0) {
            //     this.employees[i].status="Ngưng Sử Dụng";
            // }
            // else{
            //     if(this.employees[i].status==1)
            //     this.employees[i].status="Đang Sử Dụng";
            // }
            for(let j =0;j<this.departments.length;j++){
                if(this.employees[i].departmentId == this.departments[j].departmentId){
                    this.employees[i].departmentName=this.departments[j].departmentName;
                }
            }
        }
        // console.log(this.employees[0]);
    }
}



</script>

<style>
table .title{
    text-transform: uppercase;
}
span{
    font-weight: bold;
}
.display-none{
    display: none;
}
.list-function{
    position: relative;
    background-color: #ffffff;
}
</style>
