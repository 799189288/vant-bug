<template>
  <div class="hello">
    <div class="tabBar">
      <van-tabs v-model="active" @click="goto">
        <van-tab
          :title="i.title"
          v-for="(i, index) in fake"
          :key="index"
        ></van-tab>
      </van-tabs>
    </div>
    <div class="container">
      <div
        v-for="(i, index) in desti"
        :key="index"
        :id="'data' + index"
        class="title"
        ref="desti"
      >
        {{ i }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      active: 0,
      desti: [],
      fake: [
        {
          title: "1",
          main: {
            content: "这是一个内容",
            time: "2019-01-01",
          },
        },
        {
          title: "2",
          main: {
            content: "这是一个内容",
            time: "2019-01-01",
          },
        },
        {
          title: "3",
          main: {
            content: "这是一个内容",
            time: "2019-01-01",
          },
        },
        {
          title: "4",
          main: {
            content: "这是一个内容",
            time: "2019-01-01",
          },
        },
        {
          title: "5",
          main: {
            content: "这是一个内容",
            time: "2019-01-01",
          },
        },
        {
          title: "6",
          main: {
            content: "这是一个内容",
            time: "2019-01-01",
          },
        },
        {
          title: "7",
          main: {
            content: "这是一个内容",
            time: "2019-01-01",
          },
        },
        {
          title: "8",
          main: {
            content: "这是一个内容",
            time: "2019-01-01",
          },
        },
      ],
    };
  },
  methods: {
    goto(name) {
      this.$refs.desti[name].scrollIntoView({
        behavior: "smooth",
        block: "start",
      });
    },
  },
  mounted() {
    this.desti = this.fake.map((i) => i.title);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container {
  overflow: auto;
  margin-top: 50px;
  .title {
    height: 500px;
    background: #f5f5f5;
    text-align: center;
  }
}
.tabBar {
  position: fixed;
  width: 100%;
  top: 0;
}
</style>
