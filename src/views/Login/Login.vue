<template>
    <div class="login">
        <div class="login-container">
            <el-form :model="ruleForm" :rules="rules" ref="ruleForm" class="demo-ruleForm">
                <el-form-item label="" prop="username">
                    <el-input v-model="ruleForm.username" prefix-icon="el-icon-user"></el-input>
                </el-form-item>
                <el-form-item label="" prop="password">
                    <el-input v-model="ruleForm.password" prefix-icon="el-icon-lock">
                        <template #suffix>
                            <i class="el-input__icon el-icon-view"></i>
                        </template>
                    </el-input>
                </el-form-item>
                <el-form-item>
                   <el-row>
                       <el-col :span='12'>
                           <el-checkbox v-model="checked">记住密码</el-checkbox>
                       </el-col>
                       <el-col :span='12'>
                           <el-link type='primary'>{{ isLogin ? '注册账号' : '返回登录' }}</el-link>
                       </el-col>
                   </el-row>
                </el-form-item>
                <el-form-item>
                    <el-button class="submit">确定</el-button>
                </el-form-item>
            </el-form>    
        </div>
    </div>
</template>
<script>
import { reactive , toRefs} from 'vue'
// import { useRouter } from 'vue-router'
// import { useStore } from 'vuex'
export default {
    setup(){
        // const router = useRouter()
        // const store = useStore()
        const state = reactive({
            checked: false,
            isLogin: true,
            ruleForm:{
                username: '',
                password: ''
            },
            rules:{
                username: [
                    { required: true, message: '请输入活动名称', trigger: 'blur' },
                    { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
                ],
                password: [
                    { required: true, message: '请输入活动名称', trigger: 'blur' },
                    { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
                ],
            }
        })
        return {
            ...toRefs(state)
        }
    }
}
</script>
<style lang="scss" scoped>
.login{
    position: relative;
    width: 100%;
    height: 100vh;
    &-container{
        width: 380px;
        border: 1px solid #f4f5f6;
        border-radius: 5px;
        padding: 0 30px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        .submit{
            width: 100%;
        }
    }
}
</style>