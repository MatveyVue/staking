<template>
<div class="header" style="text-align: center;">
  <img class="profile" width="150px" src="https://github.com/MatveyVue/gift/blob/main/Anonim.png?raw=true">
  <h2 class="nickname" style="color: white;">{{ user }}</h2>
</div>
    
<div class="background">
<div class="psfixed">
<RouterLink style="text-decoration: none;" to="/">
    <p class="staking">Staking</p>
</RouterLink>
    <hr style="position: fixed;  width: 80px; float: left; margin-left: 10px; margin-top: 45px; border: 0.5px solid white; border-radius: 25px;">

<div class="container">
<div v-for="(person, index) in calendar" :key="index" class="gifts">
    <img style="width: 100px; margin-top: 20px;" class="icon" :src="person.icon" alt="Calendar Icon" v-if="person.icon">
    <p class="name">{{ person.name }}</p>
    <p class="locked">Total Locked: {{ person.total }}</p>
    <p class="reward">Total Reward/Days: {{ person.reward }}</p>
    <p class="time">Total Times: {{ person.time }}</p>
</div>
</div>

<p class="steaked">Steaked</p>

<div class="outer-container">
<div v-for="(person, index) in stcalendar" :key="index" class="gifts">
<div class="usercont">
    <img style="width: 80px; margin-left: -5px; border-radius: 15px;" class="icon" :src="person.icon" alt="Calendar Icon" v-if="person.icon">
    <p class="nameuser">{{ person.name }}</p>
    <p class="timeuser">{{ person.time }}</p>
</div>
</div>
</div>

</div>
</div>

</template>
    
<script setup>
import { calendar } from '/src/views/main/home.js'; 
import { stcalendar } from '/src/views/staked/staked.js'; 
</script>

<script>
export default {
  data() {
    return {
      user: window.Telegram.WebApp.initDataUnsafe.user ? window.Telegram.WebApp.initDataUnsafe.user.username : null 
    };
  },
};
</script>

<style scoped>
body {
  background-color: rgb(1, 1, 1);
  overflow-x: hidden;
  background-attachment: fixed;
  -ms-overflow-style: none;
  scrollbar-width: none;
  margin: 0;
  font-family: Inter;
  touch-action: none;
}

.name {
  color: white;
  font-family: Inter;
  margin-left: 130px;
  margin-top: -100px;
}

.nameuser {
  color: white;
  font-family: Inter;
  margin-left: 120px;
  margin-top: -55px;
}

.timeuser {
  color: white;
  font-family: Inter;
  margin-left: 70vw;
  margin-top: -35px;
}

.outer-container {
  display: flex;
  flex-direction: column;
  gap: 90px;
}
</style>
