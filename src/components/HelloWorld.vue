<script setup>
import { ref } from 'vue'
import{sayHello} from "../api/hello.js";

defineProps({
  msg: String
})

const count = ref(0)
const message=ref("music bird 后台")
const  hi=()=>{
  sayHello().then(res=>{
    console.log(res)
    message.value=res.data
  })
  //message.value="已经请求" //改变message值
}
</script>

<template>
  <h1>{{message}}</h1>

    <q-btn color="primary" @click="count++">点击次数{{count}}</q-btn>
  <hr>
  <hr>
    <q-btn color="primary" @click="hi">请求接口</q-btn>


</template>

<style scoped>
.read-the-docs {
  color: #888;
}

</style>
