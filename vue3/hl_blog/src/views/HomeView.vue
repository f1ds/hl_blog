<script setup>
  import {
    ref
  } from 'vue'

  const index = ref(0)

  window.setInterval(() => {
    if (index.value < colorList.value.length - 2) {
      index.value++
    } else {
      index.value = 0
    }

  }, 1000)

  const colorList = ref([
    '#ff7f50',
    '#0066aa',
    '#f08989',
    '#f0171b',
    '#c102f0',
    '#a6af00',
    '#ff0000',
    '#ff00ff',
    '#55ffff',
  ])
</script>

<template>
  <HeadBox></HeadBox>
  <div class="main">
    <div class="profile-photo"
      :style="{background: `linear-gradient(54deg, ${colorList[index]}, ${colorList[index+1]})`}">
      <div class="profile-img">
        <img src="https://pic.imgdb.cn/item/672341f5d29ded1a8c20942e.jpg" alt="" />
      </div>
    </div>
    <div class="text">欢迎来到虎狼的个人博客</div>

  </div>
</template>

<style scoped lang="less">
  .main {
    width: 31.25rem;
    height: 31.25rem;
    margin: 5.125rem auto;

    .profile-photo {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 15.625rem;
      height: 15.625rem;
      border-radius: 1000px;
      margin: 0.625rem auto;

      .profile-img {
        width: 14rem;
        height: 14rem;
        overflow: hidden;
        border-radius: 1000px;
        background-color: #ffffff;


        img {
          width: 100%;
          height: 100%;
          transition: all .5s;

          &:hover {
            transform: scale(1.2);
          }
        }


      }

    }

    .text {
      margin-top: 3.125rem;
      text-align: center;
      font-size: 2.8125rem;
      color: #ffffff;
      font-weight: 700;
    }
 }
</style>
