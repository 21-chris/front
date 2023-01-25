<template>
  <div class="hello">
    <div class="box">
      <div class="f2" style = 'width: 300px;height: 300px;border: 1px solid salmon;'>
        <div class="box">
          <div class="f1" >昵称</div>
          <el-input class="f4" 
          v-model="username" placeholder="请输入内容"></el-input>
        </div>
        <div class="box">
          <div class="f1">密码</div>
          <el-input class="f4" v-model="password" placeholder="请输入内容"></el-input>
        </div>
        <div >
          <el-button @click = "regist('regist')">注册</el-button>
          <el-button @click = "regist('login')">登陆</el-button>
        </div>
      </div>
      <div class="f8">注册页面</div>

    </div>
    
  </div>
</template>

<script>
export default {
  name: 'Regist',
  props: {
    msg: String
  },
  data(){
    return{
      username:'',
      password:'',
      tables:[
        
      ]
    }
  },
  created(){
for(let i =0 ;i<=10;i++){
  let ddd = []
  for(let j =0 ;j<=10;j++){
    ddd.push(
      {
        id:j,
        hang:`第${j}行`
      }
    )

  }
  this.tables.push(
    {
        id:i,
        ind:ddd
      } 
    )

}
console.log(' this.tables', this.tables)
  },
  methods:{
    regist(type){
      let url
      if(type =='regist'){
        url = '/user/regist'
      }else{
        url = '/user/login'
      }
      this.axios.post(url, {
        name: this.username,
        password: this.password,
      })
      // this.$router.push({ path: '/foo' })
    }

  }
}
</script>

<style scoped>
</style>
