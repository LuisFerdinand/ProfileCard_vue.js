<script setup>
import { ref } from 'vue'

const profileData = ref([
      {
        picture: "home.png",
        fullname: "Joko Keladi",
        address: "Jl. Meteor VI No. 198",
        hobi: ["futsal.jpg", "catur.jpg"]
      },
      {
        picture: "water.png",
        fullname: "Alex Silalahi",
        address: "Jl. Pandan X No. 30",
        hobi: ["renang.jpg", "tinju.jpg", "sepak bola.jpg"]
      },
      {
        picture: "star.png",
        fullname: "Subir Kompani",
        address: "Jl. Sekar Buana V No. 11",
        hobi: ["bulu_tangkis.jpg", "futsal.jpg", "catur.jpg"]
      }
])
</script>

<template>
  <div class="card-container">
    <div v-for="(profile, index) in profileData" :key="index" class="card">
      <div class="profile-info">
        <div class="picture">
          <img :src="profile.picture" alt="Profile Picture" />
        </div>
        <div class="fullname-address">
          <p >Fullname: {{ profile.fullname }}</p>
          <p >Address: {{ profile.address }}</p>
        </div>
      </div>
      <div class="hobbies">
        <p class="profile-hobbies">Hobbies:</p>
        <div class="hobbies-list">
          <img v-for="hobby in profile.hobi" :src="hobby" :key="hobby" alt="Hobby Image" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card-container {
  display: flex;
  flex-direction: column;
}

.card {
  margin-top: 5px;
  display: flex;
  border: 1px solid hsl(0, 0%, 80%);
  width: auto;
}

.profile-info {
  display: flex;
  margin-right: auto;
}

.picture {
  flex: 1;
  margin-right: auto;
}


.fullname-address {
  flex: 2;
}

.hobbies {
  margin-top: 10px;
  padding-top: 10px;
}
</style> 
