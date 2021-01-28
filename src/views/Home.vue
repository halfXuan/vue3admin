<!--
 * @Author: 471826078@qq.com
 * @name: 
 * @Date: 2021-01-26 15:41:57
-->
<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <button @click="add">ADD</button>
    <button @click="register">register</button>
    <button @click="login">login</button>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'Home',
//   components: {
//     HelloWorld
//   },
  data(){},
  mounted(){
     axios.get('api/string').then(res=>{
         console.log(res);
     }) 
  },
  methods:{
        add(){
            axios.post('api/add',{title: '测试',cate: '转载1',avatar: 122}).then(res=>{
                console.log(res);
            })   
        },
        register(){
            axios.post('api/users/register',{username: '测试',password: '转载1'}).then(res=>{
                console.log(res);
            }) 
        },
        login(){
             axios.post('api/users/login',{username: '测试',password: '转载1'}).then(res=>{
                console.log(res);
            }) 
        }
  }
}
</script>
