<template>
  <div class="detail">
    <h1 class="detail-title" v-text="detail.title"></h1>
    <div class="detail-body" v-html='detail.body'>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'detail',
    data() {
      return {
        detail: ''
      }
    },
    methods: {
      fetchData: function () {
        this.$http.get("//zhihudaily.p.oonnnoo.com" + "/api/4/news/" + this.$route.params.id)
          .then((response) => {
            this.detail = response.data;
            console.log(response.data);
          })
          .catch((err) => {
            console.log(err);
          })
      }
    },

    created() {
      // 组件创建完后获取数据，
      // 此时 data 已经被 observed 了
      this.fetchData()
    },
  }

</script>

<style>
  .detail {
    margin: 0 auto;
    padding: 0 0;
    width: 800px;
    max-width: 100%;
    text-align: left;
  }

  .detail img {
    max-width: 100%;
  }

  .detail-title {
    background: #fff;
    padding: 0 20px;
  }

  .detail-body {
    margin: 10px 0;
    background: #fff;
  }

  .question-title {
    padding: 20px 0;
  }

  .view-more {
    text-align: center;
    color: #698ebf;
    text-decoration: underline;
  }

  .question {
    padding-bottom: 20px;
    border-bottom: 5px solid #f6f6f6;
    padding: 0 40px 20px;
  }

</style>
