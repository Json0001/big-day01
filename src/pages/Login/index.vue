<template>
  <div class="login">

<div class="v">
    <video class="f"  id="bgvid" playsinline="" autoplay muted loop="">
        <source src="http://chst.vip:8081/stu2/media/bg_video.d2d602a9.mp4" type="video/mp4">
    </video>
</div>

    <el-form
      :model="loginForm"
      status-icon
      :rules="rules"
      ref="loginForm"
      label-width="100px"
      class="demo-loginForm"
    >
    <h1>千锋管理系统</h1>
      <el-form-item label="用户名" prop="username">
        <el-input
          type="text"
          v-model="loginForm.username"
          autocomplete="off"
        ></el-input>
      </el-form-item>
      <el-form-item label="密码" prop="password">
        <el-input
          type="password"
          v-model="loginForm.password"
          autocomplete="off"
        ></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="info"  @click="submitForm('loginForm')"
          >提交</el-button
        >
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
  //用户名框
  data() {
    var validateusername = (rule, value, callback) => {
      /* callback 校验通过不传参  不通过传参 */
      if (value === "") {
        callback(new Error("请输入用户名"));
      } else {
        // var patrn = /^[a-zA-Z]{1}([a-zA-Z0-9]|[._]){4,19}$/;
        // if (!patrn.exec(value)) {
        //   callback(new Error("用户名不规范"));
        // } else {
        //   callback();
        // }
         callback();
      }
    };
    //密码框
    var validatepassword = (rule, value, callback) => {
      if (value === "") {
        callback(new Error("请输入密码"));
      } else {
        callback();
      }
    };
    return {
      loginForm: {
        username: "",
        password: ""
      },
      rules: {
        username: [{ validator: validateusername, trigger: "blur" }],
        password: [{ validator: validatepassword, trigger: "blur" }]
      }
    };
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {   //代表本地校验通过 后期

          alert("submit!");
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }
};
</script>
<style scopde>
.el-form{
  width: 400px;
  background-color: rgba(0, 0, 0, 0.1);
  box-shadow: 0 0 .25rem rgba(95, 95, 95, .48);
  height: 500px;
}
.login h1{
  text-align: center;
  margin-top: 90px;
  margin-bottom: 50px;
  color: white;
  font-weight:900;
  font-size:35px;
}

.el-form{
  position: absolute;
  right: 160px;
    top: 100px;
}
.login label{
  color: white;
}
.login input{
    background-color:transparent;
  border:1px solid white;
}
.login button{
 background:linear-gradient(90deg,#ccc,rgb(42, 7, 241)) ; 
 width: 241px;
}
.f{
    position: absolute;
    top: 50%;
    left: 50%;
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
    z-index: -9999;
    -webkit-transform: translateX(-50%) translateY(-50%);
    transform: translateX(-50%) translateY(-50%);
    -webkit-transition: 1s opacity;
    transition: 1s opacity;
	background-color:skyblue;
	

  }
   .v{
     position: fixed;
    width: 100%;
    height: 100%;
    overflow: hidden;
    z-index: -10000; 
	background-color:skyblue;

  

   }
  .v:before{
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    display: block;
    z-index: -1000;
    top: 0;
    left: 0;
    background: rgba(90,20,10,.2);
   
   
   } 
</style>