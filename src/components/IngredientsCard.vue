<template>
    <div class="">
        <div class="max-w-sm">
  <ul class="cards">
    <li class="cards_item">
      <div class="card">
        <div class="card_image">
            <!-- img -->
          <img :src="imgSrc" alt="imagen ingrediente" />
          <!-- <span class="card_price"><span>$</span>9</span> -->
        </div>
        <div class="card_content">
          <!-- Main title -->
          <h2  class="text-yellow-600 card_title font-poppins">{{  mainTitle }}</h2>
          <div class="card_text">
            <!-- small intro -->
            <p class="font-poppins">
              {{ smallIntro }}
            </p>
            <hr />
            <!-- description -->
            <p class="font-poppins">{{ description }}
            </p>
            <hr>
            <!-- list info -->
             <ul>
              <li class="mb-2 text-sm font-poppins" v-for="item in infoArr" :key="item.id"><strong class="text-yellow-700">{{ item.property }}:</strong> {{ item.description }}</li>
              <hr>
             </ul>
          </div>
        </div>
      </div>
    </li>
  </ul>
</div>
    </div>
</template>

<script lang="ts" setup>

const props = defineProps({
  mainTitle: String,
  smallIntro: String,
  description: String,
  imgSrc: String,
  infoArr:{
    type: Array,
     default: () => [] 
  },
  titleColor: String
})

</script>

<style scoped>

*,
*::before,
*::after {
  box-sizing: border-box;
}


.cards {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  margin: 0;
  padding: 0;
}

.cards_item {
  display: flex;
  padding: 1rem;
}

.card_image {
  position: relative;
  max-height: 250px;
}

.card_image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card_price {
  position: absolute;
  bottom: 8px;
  right: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 45px;
  height: 45px;
  border-radius: 0.25rem;
  background-color: #c89b3f;
  font-size: 18px;
  font-weight: 700;
}

.card_price span {
  font-size: 12px;
  margin-top: -2px;
}

.note {
  position: absolute;
  top: 8px;
  left: 8px;
  padding: 4px 8px;
  border-radius: 0.25rem;
  background-color: #c89b3f;
  font-size: 14px;
  font-weight: 700;
}


.card {
  background-color: white;
  border-radius: 0.25rem;
  box-shadow: 0 20px 40px -14px rgba(0, 0, 0, 0.25);
  display: flex;
  flex-direction: column;
  /* overflow: hidden; */
}

.card_content {
  position: relative;
  padding: 16px 12px 32px 24px;
  margin: 16px 8px 8px 0;
  /* max-height: 290px; */
  /* overflow-y: scroll; */
}

.card_content::-webkit-scrollbar {
  width: 8px;
}

.card_content::-webkit-scrollbar-track {
  box-shadow: 0;
  border-radius: 0;
}

.card_content::-webkit-scrollbar-thumb {
  background: #c89b3f;
  border-radius: 15px;
}

.card_title {
  position: relative;
  margin: 0 0 24px;
  padding-bottom: 10px;
  text-align: center;
  font-size: 20px;
  font-weight: 700;
}

.card_title::after {
  position: absolute;
  display: block;
  width: 50px;
  height: 2px;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  background-color: #c89b3f;
  content: "";
}

hr {
  margin: 24px auto;
  width: 50px;
  border-top: 2px solid #c89b3f;
}

.card_text p {
  margin: 0 0 24px;
  font-size: 14px;
  line-height: 1.5;
}

.card_text p:last-child {
  margin: 0;
}

</style>