<template>
  <Tabs value="1" class="msg-tabs" :animated="false">
    <TabPane label="水务要闻" name="1">
      <div class="line"></div>
      <div class="row" v-for="(item, i) in ShuiWuList" :key="i">
        <div class="col-0"><div class="circle"></div></div>
        <div class="col-1">{{ item.title }}</div>
        <div class="col-2">{{ item.date }}</div>
      </div>
    </TabPane>
    <TabPane label="地方水事" name="2">标签二的内容</TabPane>
    <TabPane label="基层工作" name="3">标签三的内容</TabPane>
    <TabPane label="热点导读" name="4">标签四的内容</TabPane>
  </Tabs>
</template>

<script>
export default {
  data() {
    return {
      ShuiWuList: [
        {
          title: "丰县大沙河国家级水利风景区 再添1个国家级、3个省级水利风景区",
          date: "2021-01-15",
        },
        {
          title: "新建成的丰县付庄水厂 全市城乡供水一体化新格局基本形成",
          date: "2020-12-23",
        },
        {
          title: "荆马河污水处理厂 《徐州市排水与污水处理条例》通过审议",
          date: "2020-11-05",
        },
        {
          title: "新城区大龙湖 最严格水资源管理进入全省优秀方阵",
          date: "2020-10-18",
        },
        { title: "有效应对1960年以来沂沭泗地区最大洪水", date: "2020-09-22" },
        {
          title: "启动实施城镇污水处理提质增效三年行动 和精准攻坚“333”行动",
          date: "2020-09-10",
        },
        { title: "全面实现城乡供水一体化入户全覆盖", date: "2020-08-18" },
        {
          title:
            "有效保障全省最缺水的南四湖湖西地区284万人、 占全市1/3耕地的发展用水需求",
          date: "2020-05-03",
        },
        {
          title: "率先通过农业水价综合改革省级验收 农业水价综合改革验收",
          date: "2020-03-07",
        },
        { title: "全力推动河湖长制深化发展", date: "2020-03-01" },
        { title: "全面整治河湖“两违三乱”", date: "2020-02-10" },
        { title: "积极构筑全域生态美丽河湖格局", date: "2020-01-25" },
      ],
    };
  },
};
</script>

<style lang="less" scoped>
.msg-tabs {
  height: 100%;

  /deep/ .ivu-tabs-bar {
    // navbar与content距离
    // margin-bottom: 0;

    .ivu-tabs-nav {
      font-size: 2vh;
      color: @theme-black;
      width: 100%;

      .ivu-tabs-tab {
        width: 25%;
        margin: 0;
        &.ivu-tabs-tab-active,
        &:hover {
          color: @theme-blue;
        }
      }
      .ivu-tabs-ink-bar {
        background-color: @theme-blue;
        bottom: 0;
        height: 3px;
      }
    }
  }

  /deep/ .ivu-tabs-content {
    height: calc(100% - 61px); // 100% - 45px - 16px 自带margin-top:16px
    overflow-y: auto;
    .ivu-tabs-tabpane {
      position: relative;
    }
  }
  // 圆圈的竖线
  .line {
    position: absolute;
    left: 6px;
    border-right: 1px solid rgb(235, 235, 235);
    width: 0px;
    height: calc(100% - 50px); // 50是一行row的高度
    top: 25px; // 50/2
  }

  .row {
    line-height: 50px;
    color: @theme-black;
    height: 50px;

    &:hover {
      color: @theme-blue;
      cursor: pointer;
      & .col-0 .circle::after {
        background-color: @theme-blue;
      }
    }
    .col-1,
    .col-2,
    .col-0 {
      display: inline-block;
      vertical-align: middle;
    }
    // 圆圈
    .col-0 {
      position: absolute;
      width: 0px;
      .circle {
        display: inline-block;
        width: 12px;
        height: 12px;
        background-color: #fff;
        line-height: 0;
        vertical-align: middle;

        &::after {
          content: "";
          display: inline-block;
          background-color: rgb(216, 216, 216);
          width: 8px;
          height: 8px;
          border-radius: 50%;
          margin-top: 2px;
        }
      }
    }
    .col-1 {
      font-size: 1.8vh;
      width: 75%;
      margin-left: 5%;
      text-align: left;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
      border-bottom: 1px dashed rgb(216, 216, 216);
    }
    .col-2 {
      font-size: 1.6vh;
      width: 20%;
      text-align: center;
      border-bottom: 1px dashed rgb(216, 216, 216);
    }
  }
}
</style>