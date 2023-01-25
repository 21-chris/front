<template>
  <div class="hello">
    <div class="box">
      <div class="f5">注册页面</div>

      <div class="f5" style = 'width: 300px;height: 300px;border: 1px solid salmon;'>
        <div class="box">
          <n-input-group-label class="f1" >昵称</n-input-group-label>
          <n-input class="f4" 
          v-model="username" placeholder="请输入内容"></n-input>
        </div>
        <div class="box">
          <div class="f1 boxColumnCenter" >密码</div>
          <n-input class="f4" v-model="password" placeholder="请输入内容"></n-input>
        </div>
        <div >
          <n-button @click = "regist('regist')">注册</n-button>
          <n-button @click = "regist('login')">登陆</n-button>
        </div>
      </div>
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
