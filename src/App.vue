<script setup>
// import HelloWorld from './components/HelloWorld.vue'
import Api from './components/api.vue'

const handleUserClick = (user) => {
  console.log("收到的 user 資料：", user)
  alert(`${user.name}被你點到了`)
}
</script>

<template>
  <div>
    <Api @userClicked="handleUserClick"/>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
