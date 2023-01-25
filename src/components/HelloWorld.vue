<script setup>
import { reactive , ref} from 'vue'
import { useRouter } from 'vue-router';
const state = reactive({ count: 0 })
const router = useRouter()
defineProps({
  msg: {
    type: String,
    required: true
  }
})
function regist(event) {
  if(event){
    console.log("----",event)
    router.push({ path: '/Regist' })
  }
}
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
    <div @click = "regist('regist')">注册</div>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
