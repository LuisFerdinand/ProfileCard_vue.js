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
  align-items: center;
}

.card {
  margin-top: 5px;
  display: flex;
  flex-direction: column;
  border: 1px solid hsl(0, 0%, 80%);
  padding: 10px;
  width: 400px;
}

.profile-info {
  display: flex;
  align-items: center;
}

.picture {
  flex: 1;
  margin-right: 10px;
}

.picture img {
  width: 150px;
  height: 150px;
  object-fit: cover;
}

.fullname-address {
  flex: 2;
  border-left: 1px solid hsl(0, 0%, 80%);
  padding-left: 10px;
}

.hobbies {
  margin-top: 10px;
  border-top: 1px solid hsl(0, 0%, 80%);
  padding-top: 10px;
}

.profile-hobbies {
  font-weight: bold;
  margin-bottom: 5px;
}

.hobbies-list {
  display: flex;
  flex-wrap: wrap;
}

.hobbies-list img {
  width: 70px;
  height: 70px;
  object-fit: cover;
  margin-right: 5px;
  margin-bottom: 5px;
}

.profile-info > * {
  border-right: 1px solid hsl(0, 0%, 80%);
  padding-right: 10px;
}
</style> 
