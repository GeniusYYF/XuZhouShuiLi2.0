<template>
  <Row class="titles">
    <div class="item" v-for="(item, i) in sysList" :key="i" span="2">
      <img
        class="img"
        :src="require(`@/assets/integration/home/${item.icon}.png`)"
      />
      <div class="title">{{ item.title }}</div>
    </div>
  </Row>
</template>

<script>
export default {
  data() {
    return {
      sysList: [
        // 防汛抗旱、城市供水、南水北调、工程管理、水资源管理、农村水利、城镇排水、河长监督、河湖管理、水土保持、协同办公
        { title: "防汛抗旱", icon: "5" },
        // { title: "供水管理", icon: "6" },
        // { title: "排水管理", icon: "7" },
        { title: "城市供水", icon: "6" },
        { title: "南水北调", icon: "8" },
        { title: "工程管理", icon: "9" },
        { title: "水资源管理", icon: "10" },
        { title: "农村水利", icon: "11" },
        { title: "城镇排水", icon: "1" },
        { title: "河长监督", icon: "2" },
        { title: "河湖管理", icon: "3" },
        { title: "水土保持", icon: "4" },
        { title: "协同办公", icon: "12" },
      ],
    };
  },
};
</script>

<style lang="less" scoped>
.titles {
  // margin-top: -100px;
  // height: 100px;
  // background-color: rgba(0, 0, 0, 0.5);
  background-color: #515a6e; // #2db7f5 #5cadff #2b85e4 #2d8cf0  19be6b 515a6e 808695 17233d c5c8ce
  padding: 12px 10px;
  position: relative; // 防止被图片的relative覆盖背景色

  .item {
    // col 拥有样式
    position: relative;
    max-width: 100%;
    min-height: 1px;
    display: block;
    -webkit-box-flex: 0;
    -ms-flex: 0 0 9.09090909%; // 100/11
    flex: 0 0 9.09090909%;
    max-width: 9.09090909%;
    // 自定义
    line-height: 1;

    .img {
      border-radius: 50%;
      // background-color:rgb(0,146,215);
      
      width: 6.2vh;
    }

    &:hover {
      cursor: pointer;
      .img {
        // background-color:rgba(@theme-blue, .3);
        box-shadow: inset 0 5px 10px rgba(@theme-blue, 0.5);
      }
      .title {
        color: @theme-blue;
      }
    }

    .title {
      color: rgb(255, 255, 255);
      font-size: 1.8vh; // 与图片一齐固定大小
    }
  }
}
</style>