<script setup>
  import { ref } from 'vue'
  import { useRouter } from 'vue-router'
  const router = useRouter()
  const dataList = ref([
    {
      url:'https://pic.imgdb.cn/item/67220ba6d29ded1a8c46159a.png',
      title:'首页',
      path:'/about'
    },
    {
      url:'https://pic.imgdb.cn/item/6722dd55d29ded1a8c942618.png',
      title:'文章',
      path:'/about'
    },
    {
      url:'https://pic.imgdb.cn/item/6722df1ed29ded1a8c96e020.png',
      title:'音乐',
      path:'/about'
    },
    {
      url:'https://pic.imgdb.cn/item/6722dec5d29ded1a8c965dc0.png',
      title:'API',
      path:'/about'
    },
    {
      url:'https://pic.imgdb.cn/item/6722dda3d29ded1a8c94a2ef.png',
      title:'关于',
      path:'/about'
    },
  ])

  const activeIndex = ref(0)


  const onClick = (path) => {
    router.push(path)
    console.log(123213)
  }

  const clickInput = () => {
    console.log(123)
  }
</script>

<template>
  <header class="head">
    <div class="w">
      <div class="optionList">
        <div @click="onClick(item.path)"  class="item" :class="{ active: index === activeIndex}" v-for="(item,index) in dataList" :key="index">
          <img :src="item.url" alt="" />
          {{ item.title }}
        </div>


      </div>
      <div class="head-input">
        <el-input @click="clickInput" style="width: 240px" placeholder="搜索" />
      </div>
    </div>

  </header>
</template>

<style scoped lang="less">
  .head {
    width: 100%;
    max-width: 1800px;
    height: 50px;
    display: flex;
    align-items: center;
    backdrop-filter: blur(7px);
    background-color: rgba(255, 255, 255, 0.3);
    color: black;
    font-size: 20px;

    .w {
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .optionList {
      display: flex;
      align-items: center;
      overflow: hidden;
      height: 100%;
      padding-left: 50px;

      .item {
        display: flex;
        align-items: center;
        width: 93px;
        height: 50px;
        transition: all 0.5s;

        &:hover {
          cursor: pointer;
          transform: scale(1.2);

        }

        img {
          width: 30px;
          height: 30px;
          margin-right: 5px;
        }

        margin-right: 50px;
      }
      .active {
        border-bottom: 3px solid #ffffff;
      }
      .head-input {
        flex: 1;
        justify-content: end;
      }
    }

  }
</style>
