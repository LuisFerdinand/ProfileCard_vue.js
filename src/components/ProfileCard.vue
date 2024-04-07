<script setup>
import { ref } from 'vue'

const profileData = ref([
  {
    picture:
      'https://media.licdn.com/dms/image/D5603AQHx_hCVsyya_Q/profile-displayphoto-shrink_800_800/0/1694454119626?e=2147483647&v=beta&t=U5EkoQIrnfHTZDB0jdPC9IZTdQ6Qh6FeInKdMO7Ddyk',
    fullname: 'Joko Keladi',
    address: 'Jl. Meteor VI No. 198',
    hobi: [
      'https://upload.wikimedia.org/wikipedia/commons/0/06/Futebol_Salao_Pan2007.jpg',
      'https://play-lh.googleusercontent.com/vj2IpdfGBoz5uIEY0UjGqDhSghy9IpnHuJm7zztuxZaNhLhgmTwX6QVX9f4mxCpm-GI=w526-h296-rw'
    ]
  },
  {
    picture:
      'https://media.licdn.com/dms/image/C5603AQH41Hm2YNP3IQ/profile-displayphoto-shrink_400_400/0/1647149823202?e=2147483647&v=beta&t=-vx3Jq0pV8roUER0Hjjl-MYHowfESRz-GKlJWEpscQE',
    fullname: 'Alex Silalahi',
    address: 'Jl. Pandan X No. 30',
    hobi: [
      'https://www.health.com/thmb/Yv4HuoQyNbHNNxgtOTm63zqxurQ=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/Health-Swimming-080c78802f384a4687df5a3b13d5611e-3719a8e40a3c4c43a63a4d795e47c505.jpg',
      'https://a.espncdn.com/media/motion/2023/1028/dm_231028_dm_231028_BOX_Fury_Ngannou_pub2tag/dm_231028_dm_231028_BOX_Fury_Ngannou_pub2tag.jpg',
      'https://i.ytimg.com/vi/BSZy2MorHTk/maxresdefault.jpg'
    ]
  },
  {
    picture:
      'https://image.cnbcfm.com/api/v1/image/103979967-20160928-0666-2283.jpg?v=1530879569&ffmt=webp&w=400&h=300',
    fullname: 'Subir Kompani',
    address: 'Jl. Sekar Buana V No. 11',
    hobi: [
      'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQsaOcgNjhLCOacn8yXk1dCNbM7LoA10hrV4f8zTf7m1Q&s',
      'https://upload.wikimedia.org/wikipedia/commons/0/06/Futebol_Salao_Pan2007.jpg',
      'https://play-lh.googleusercontent.com/vj2IpdfGBoz5uIEY0UjGqDhSghy9IpnHuJm7zztuxZaNhLhgmTwX6QVX9f4mxCpm-GI=w526-h296-rw'
    ]
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
