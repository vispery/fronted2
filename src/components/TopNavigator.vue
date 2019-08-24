<template>
  <div id="TopNavigator">
    <el-menu
      :default-active="activeIndex2"
      class="el-menu-demo"
      mode="horizontal"
      @select="handleSelect"
      background-color="#545c64"
      text-color="#fff"
      active-text-color="#ffd04b"
    style="width: 100%">
      <el-menu-item index="1">
        <el-avatar class="el-icon-school"></el-avatar>
      </el-menu-item>
      <el-menu-item index="9" class="input">
        <el-input
          placeholder="请输入内容"
          v-model="input4">
          <i slot="prefix" class="el-input__icon el-icon-search"></i>
        </el-input>
      </el-menu-item>
      <el-menu-item index="1" class="aboutus" @click="dialogTableVisible = true">联系我们</el-menu-item>
      <el-menu-item index="1" class="login" @click="dialogFormVisible=true">{{logininf}}</el-menu-item>
      <el-menu-item index="1">
        <el-badge :value="1" class="item">
          <el-dropdown>
      <span class="el-dropdown-link">
              <el-avatar :size="50" :src="circleUrl" class="avatar el-icon-user">
      </el-avatar>
      </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item icon="el-icon-phone">我的报修</el-dropdown-item>
              <el-dropdown-item icon="el-icon-warning">我的投诉</el-dropdown-item>
              <el-dropdown-item icon="el-icon-user">个人信息</el-dropdown-item>
              <el-dropdown-item icon="el-icon-close" @click.native="exit">退出</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </el-badge>
      </el-menu-item>
    </el-menu>

    <el-dialog title="联系我们" :visible.sync="dialogTableVisible">
      <contactUs></contactUs>
    </el-dialog>
    <el-dialog title="注册/登录" :visible.sync="dialogFormVisible">
      <el-tabs v-model="activeName" type="card">

        <el-tab-pane label="注册" name="first">

          <el-form :model="ruleForm" status-icon :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
            <el-form-item label="邮箱" prop="email" >
              <el-input type="email" v-model="ruleForm.email" placeholder="请填写正确格式的邮箱"></el-input>
            </el-form-item>
            <el-form-item label="用户名" prop="Usernames" >
              <el-input  v-model="ruleForm.Usernames" placeholder="请输入3-10长度字符"></el-input>
            </el-form-item>
            <el-form-item label="密码" prop="pass" >
              <el-input type="password" v-model="ruleForm.pass" autocomplete="off" placeholder="输入密码"></el-input>
            </el-form-item>
            <el-form-item label="确认密码" prop="checkPass" >
              <el-input type="password" v-model="ruleForm.checkPass" autocomplete="off" placeholder="确认密码"></el-input>
            </el-form-item>
            <el-form-item>
              <el-button type="primary" @click="submitFormReg('ruleForm')">提交</el-button>
              <el-button @click="resetForm('ruleForm')">重置</el-button>
            </el-form-item>
          </el-form>

        </el-tab-pane>

        <el-tab-pane label="登录" name="second">
          <el-form :model="ruleForm" status-icon :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
            <el-form-item label="邮箱" prop="email">
              <el-input type="email" v-model="ruleForm.email"></el-input>
            </el-form-item>
            <el-form-item label="密码" prop="pass">
              <el-input type="password" v-model="ruleForm.pass" autocomplete="off"></el-input>
            </el-form-item>
            <el-form-item label="身份选择" prop="Id">
              <el-radio-group v-model="ruleForm.Id">
                <el-radio label="租客"></el-radio>
                <el-radio label="管理员"></el-radio>
                <el-radio label="修理人员"></el-radio>
              </el-radio-group>
            </el-form-item>
            <el-form-item>
              <el-button type="primary" @click="submitFormLogin('ruleForm')">登录</el-button>
              <el-button @click="resetForm('ruleForm')">重置</el-button>
            </el-form-item>
          </el-form>
        </el-tab-pane>
      </el-tabs>

    </el-dialog>

  </div>
</template>

<script>
  import contactUs from "./contactUs";
    export default {
        name: "TopNavigator",
        components:{
            contactUs
        },
        data() {
            var validatePass = (rule, value, callback) => {
                if (value === '') {
                    callback(new Error('请输入密码'));
                } else {
                    if (this.ruleForm.checkPass !== '') {
                        this.$refs.ruleForm.validateField('checkPass');
                    }
                    callback();
                }
            };
            var validatePass2 = (rule, value, callback) => {
                if (value === '') {
                    callback(new Error('请再次输入密码'));
                } else if (value !== this.ruleForm.pass) {
                    callback(new Error('两次输入密码不一致!'));
                } else {
                    callback();
                }
            };
            return {
                logininf:"",
                ruleForm: {
                    pass: '',
                    checkPass: '',
                    email: '',
                    Usernames: '',
                    Id: ''
                },
                input4:'',
                activeName: 'first',
                rules: {
                    pass: [
                        { required: true,validator: validatePass, trigger: 'blur' }
                    ],
                    checkPass: [
                        { required: true,validator: validatePass2, trigger: 'change' }
                    ],
                    email:[
                        { required: true, message: '请输入邮箱地址', trigger: 'change'},
                        { type: 'email', message: '请输入正确的邮箱地址', trigger: ['blur', 'change'] }
                    ],
                    Usernames: [
                        { required: true, message: '请输入用户名', trigger: 'change' },
                        { min: 3, max: 10, message: '长度在 3 到 10 个字符', trigger: ['blur', 'change'] }
                    ],

                },

                dialogTableVisible: false,
                dialogFormVisible: false,
                activeIndex: '1',
                formLabelWidth: '100px',
                imageUrl:'',
            };
        },
        updated(){
            var email = sessionStorage.getItem("email");
            console.log(email);
            if(email === null)
                this.logininf = "注册/登录";
            else
                this.logininf =  "欢迎"  + "！";
        },
        mounted(){
                var email = sessionStorage.getItem("email");
                console.log(email);
                if(email === null)
                    this.logininf = "注册/登录";
                else
                    this.logininf =  "欢迎"  + "！";
        },
        methods:{
            exit:function(){
              sessionStorage.removeItem("email");
              this.logininf = "登录/注册";
                this.$notify({
                    title: '成功',
                    message: '您已成功退出',
                    type: 'success'
                });
            },
            resetForm(formName) {
                this.$refs[formName].resetFields();
                this.Usernames='';
                this.checkPass='';
            },
            submitFormReg(formName) {
                this.$refs[formName].validate((valid) => {
                    if (valid) {
                        const url ='/api/register';
                        this.$http({
                            method: 'post',
                            url:url,
                            data:{
                                name:this.ruleForm.Usernames,
                                password:this.ruleForm.pass,
                                email:this.ruleForm.email
                            }
                        }).then((res)=>{
                            if(res.data["ok"] === true){
                                this.dialogFormVisible = false;
                                this.$notify({
                                    title: '成功',
                                    message: '您已成功注册',
                                    type: 'success'
                                });
                            }
                            else if(res.data["name"] === false){
                                this.$notify({
                                    title: '失败',
                                    message: '此用户名已被注册',
                                    type: 'warning'
                                });
                            }
                            else if(res.data["email"] === false){
                                this.$notify({
                                    title: '失败',
                                    message: '此邮箱已被注册',
                                    type: 'warning'
                                });
                            }
                        }).catch((error) => {
                            console.warn(error)
                        });
                    } else {
                        console.log('error submit!!');
                        return false;
                    }
                });
            },
            submitFormLogin(formName){
                this.$refs[formName].validate((valid) => {
                    if (valid) {
                        const url ='/api/login';
                        this.$http({
                            method: 'get',
                            url:url,
                            params:{
                                password:this.ruleForm.pass,
                                email:this.ruleForm.email
                            }
                        }).then((res)=>{
                            if(res.data["ok"] === true){
                                this.dialogFormVisible = false;
                                this.$notify({
                                    title: '成功',
                                    message: '您已成功登录',
                                    type: 'success'
                                });
                                sessionStorage.setItem("email", this.ruleForm.email);
                            }
                           else{
                                this.$notify({
                                    title: '失败',
                                    message: '身份信息验证失败',
                                    type: 'warning'
                                });
                            }
                        }).catch((error) => {
                            console.warn(error)
                        });
                    } else {
                        console.log('error submit!!');
                        return false;
                    }
                });

            },
            handleSelect(key, keyPath) {
                console.log(key, keyPath);
            }
        },

    }
</script>
<style scoped>
  .aboutus {
    margin-left: 18%;
  }

  .login {
    margin-left: 2%;
  }

  .input {
    margin-left: 20%;
    width: 25%;
  }

  .avatar {
    margin-left: 10%;

  }

  .avatar-uploader .el-upload {
    border: 1px dashed #d9d9d9;
    border-radius: 6px;
    cursor: pointer;
    position: relative;
    overflow: hidden;
  }

  .avatar-uploader .el-upload:hover {
    border-color: #409EFF;
  }
  #TopNavigator{
    padding-top: 2%;
  }

</style>
