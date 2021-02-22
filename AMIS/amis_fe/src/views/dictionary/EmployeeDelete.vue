<style scoped>
.isHideDelete{
    display: none;
}
.m-dialog {
    z-index: 999;
    position: relative;
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
.m-delete-content{
  position: fixed;
  border-radius: 5px;
  width: 420px;
  height: 180px;
  background-color: #fff;
  left: calc(50% - 150px);
  top: calc(50% - 70px);
  border: 1px solid #000000;
}
.dialog-delete-header {
  position: relative;
  height: 40px;
  line-height: 60px;
  padding-left: 16px;
  display: flex;
  font-size: 24px;
}
.dialog-header-close {
  position: absolute;
  right: 36px;
  width: 16px;
  height: 24px;
  border-radius: 50%;
  cursor: pointer;
  top: 10px;
  align-items: center;
  border:none;
  background-color: transparent;
  font-size: 24px;
  line-height: 24px;
}
.dialog-body {
  /* margin-top: 10px; */
  padding: 0 16px 16px 16px;
  position: relative;
}
    .dialog-body-image{
        background: url('../../assets/img/Sprites.64af8f61.svg') no-repeat -598px -463px;
        width: 36px;
        height: 37px;
        margin-left: 20px;
    
    }
    .dialog-body-text{
        position: absolute;
        top: 5px;
        left: 92px;
        width: 280px;
        overflow: auto;
        font-weight: normal;
    }
.dialog-footer {
  display: flex;
  width: 100%;
  height: 60px;
  margin-left: 20px;
  margin-top: 20px;
  box-sizing: border-box;
  position: relative;
}

    .m-btn-cancel{
        width: 76px;
        height: 32px;
        border: 1px solid #000;
        border-radius: 3px;
        margin-left: 16px;
        font-weight: bold;
    }
    .m-btn-save{
        position: absolute; 
        top: 0;
        right: 54px;
        width: 50px;
        height: 32px;
        border: none;
        background-color: #248b15;
        color: #fff;
        border-radius: 3px;
    }

hr{
    width: 350px;
}
</style>
<template>
  <div>
    <div
      class="m-dialog dialog-detail"
      title="Xác nhận xoá" 
      :class="{isHideDelete: isHideDelete }"
    >
        <div class="dialog-modal"></div>
      <div class="m-delete-content">
        <div class="dialog-delete-header">
          <div class="dialog-header-title"></div>
          
        </div>
        <div class="dialog-body">
          <div class="dialog-body-image"><img src="" alt=""></div>
          <span class="dialog-body-text">Bạn có thực sự muốn xoá nhân viên 	&lt;CA1&gt; không?</span>
        </div>
        <hr>
        <div class="dialog-footer">
          <button id="btnCancel" v-on:click="btnCancelDeleteOnClick" class="m-btn m-btn-default m-btn-cancel" >
            Không
          </button>
          <button id="btnSave" @click="DeleteOnClick" class="m-btn m-btn-default m-btn-save">
            <i class="far fa-save"></i><span class="btn-text">Có</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import * as axios from "axios";
export default {
  props: ['isHideDelete','employee'],
  methods: {
    btnCancelDeleteOnClick(){
      this.$emit('closeDelete',true);
    },
    async DeleteOnClick(){
        const update = await axios.delete("https://localhost:44356/api/Employees/"+this.employee.employeeId);
            
        console.log(update);
        this.$emit('closeDelete',true)
        location.reload();
    }
  },
  data() {
    return {
    };
  },
};
</script>
